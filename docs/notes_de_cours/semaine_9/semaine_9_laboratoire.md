# Laboratoire – Exécution automatique d’un script PowerShell depuis la clé USB

Ce tutoriel montre comment configurer un fichier `autounattend.xml` pour **lancer automatiquement un script PowerShell** situé sur la clé USB d’installation, sans intervention manuelle.  
Le script installe ici **Firefox via Winget**, mais la méthode fonctionne pour tout autre logiciel.

---

## 1️⃣ Structure de la clé USB

```
├── autounattend.xml
├── setup.exe
├── sources\
└── script_installation\
    └── installation.ps1
```

---

## 2️⃣ Contenu du script `installation.ps1`

Place le fichier suivant dans le dossier `script_installation` à la racine de ta clé USB :

```powershell
# script_installation\installation.ps1
Write-Output "Démarrage de l'installation de Firefox via Winget..."

if (Get-Command winget -ErrorAction SilentlyContinue) {
    winget install --id Mozilla.Firefox -e --silent
    Write-Output "Firefox a été installé avec succès !"
} else {
    Write-Output "Winget n'est pas disponible sur ce système."
}
```

---

## 3️⃣ Script PowerShell de recherche automatique

Lors du premier démarrage de Windows, un script intégré dans le fichier `autounattend.xml` parcourra tous les lecteurs pour trouver et exécuter ton `installation.ps1`.

```powershell
# Recherche et exécution du script d'installation sur n'importe quel lecteur USB
$target = 'script_installation\installation.ps1'
$found = $null

foreach ($drive in [System.IO.DriveInfo]::GetDrives()) {
    try {
        $candidate = Join-Path -Path $drive.RootDirectory.FullName -ChildPath $target
        if (Test-Path $candidate) {
            Write-Output "Script trouvé : $candidate"
            Start-Process -FilePath "powershell.exe" -ArgumentList "-ExecutionPolicy Bypass -File `"$candidate`"" -Wait
            return
        }
    } catch {
        # Ignore les lecteurs non accessibles
    }
}

Write-Warning "Aucun script d'installation trouvé sur les lecteurs connectés."
```

---

## 4️⃣ Intégration dans `autounattend.xml`

Ajoute ce bloc dans la section `<FirstLogonCommands>` :

```xml
<FirstLogonCommands>
  <SynchronousCommand wcm:action="add">
    <Order>1</Order>
    <Description>Recherche et exécution du script d'installation</Description>
    <CommandLine>powershell.exe -NoProfile -ExecutionPolicy Bypass -Command "
      $target = 'script_installation\\installation.ps1';
      $found = $null;
      foreach ($drive in [System.IO.DriveInfo]::GetDrives()) {
          try {
              $candidate = Join-Path -Path $drive.RootDirectory.FullName -ChildPath $target;
              if (Test-Path $candidate) {
                  Write-Output ('Script trouvé : ' + $candidate);
                  Start-Process -FilePath 'powershell.exe' -ArgumentList ('-ExecutionPolicy Bypass -File \\\"' + $candidate + '\\\"') -Wait;
                  return;
              }
          } catch {}
      };
      Write-Warning 'Aucun script d\\'installation trouvé sur les lecteurs connectés.';
    "</CommandLine>
  </SynchronousCommand>
</FirstLogonCommands>
```

---

## 5️⃣ Vérification et test

1. Démarre ton installation Windows avec la clé USB.  
2. L’installation se fera automatiquement.  
3. Lors du **premier démarrage**, le script PowerShell se lancera.  
4. Firefox sera installé silencieusement via Winget.  

---

## ✅ Bonnes pratiques

- Enregistre ton fichier XML en **UTF-8 sans BOM**.  
- Utilise `-ExecutionPolicy Bypass` pour éviter les blocages liés aux scripts non signés.  
- Ajoute des journaux (`Out-File`) pour le débogage :  
  ```powershell
  Write-Output "message" | Out-File -FilePath "C:\Windows\Temp\install-log.txt" -Append
  ```
- Teste d’abord sur une **machine virtuelle** avant déploiement réel.  

---

**Résultat attendu :**  
À la fin de l’installation, **Firefox est présent et fonctionnel** sans qu’aucune fenêtre ne soit apparue pendant le processus.