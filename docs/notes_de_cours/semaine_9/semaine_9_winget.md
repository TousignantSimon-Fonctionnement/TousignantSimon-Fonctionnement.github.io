# Cours Winget – Niveau Débutant à Intermédiaire

## 🧭 Objectif du cours
Apprendre à utiliser **Winget**, le gestionnaire de paquets officiel de Microsoft, pour installer, mettre à jour et gérer des logiciels sous Windows 10/11.

---

## 1️⃣ Introduction à Winget

### Qu’est-ce que Winget ?
**Winget (Windows Package Manager)** est un outil en ligne de commande permettant :
- d’installer, désinstaller et mettre à jour des applications Windows ;
- d’automatiser les installations ;
- d’exporter/importer des listes de logiciels.

### Avantages
- Intégré nativement à Windows 11 et aux versions récentes de Windows 10 ;
- Officiel et sécurisé ;
- Alternative moderne à Ninite ou Chocolatey ;
- Parfait pour scripts, administrateurs ou utilisateurs avancés.

### Vérification de la présence de Winget
Ouvrez **PowerShell** et exécutez :
```powershell
winget --version
```
S’il n’est pas reconnu, installez **App Installer** depuis le Microsoft Store.

---

## 2️⃣ Commandes de base

| Action | Commande | Exemple |
|--------|-----------|----------|
| Rechercher un logiciel | `winget search <nom>` | `winget search firefox` |
| Installer un logiciel | `winget install <id>` | `winget install Mozilla.Firefox` |
| Lister les logiciels installés | `winget list` | |
| Mettre à jour un logiciel | `winget upgrade <id>` | `winget upgrade 7zip.7zip` |
| Mettre à jour tout | `winget upgrade --all` | |
| Désinstaller un logiciel | `winget uninstall <id>` | `winget uninstall VLC` |

---

## 3️⃣ Commandes avancées

### Exporter une liste de logiciels installés
```powershell
winget export apps.json
```
Cela crée un fichier JSON contenant toutes les applications installées par Winget.

### Réimporter une liste (réinstallation automatique)
```powershell
winget import apps.json
```
Winget installe automatiquement tous les logiciels listés dans le fichier exporté.

### Gérer les sources
```powershell
winget source list
winget source update
winget source reset --force
```
Ces commandes permettent de consulter et rafraîchir les dépôts de packages.

### Modifier la configuration (fichier JSON)
```powershell
winget settings
```
Cela ouvre le fichier `settings.json` dans votre éditeur par défaut (généralement Notepad).

---

## 4️⃣ Laboratoire pratique

### 🎯 Objectif
Installer, désinstaller et réinstaller automatiquement des applications à l’aide de Winget.

### 🧪 Étapes

1. **Vérifier la version de Winget**
   ```powershell
   winget --version
   ```

2. **Rechercher et installer 3 logiciels**
   ```powershell
   winget search 7zip
   winget install 7zip.7zip

   winget search firefox
   winget install Mozilla.Firefox

   winget search vlc
   winget install VideoLAN.VLC
   ```

3. **Lister les logiciels installés**
   ```powershell
   winget list
   ```

4. **Exporter la liste des logiciels**
   ```powershell
   winget export apps.json
   ```

5. **Désinstaller un logiciel**
   ```powershell
   winget uninstall VideoLAN.VLC
   ```

6. **Réimporter la liste (réinstallation automatique)**
   ```powershell
   winget import apps.json
   ```

### ✅ Résultat attendu
- VLC est automatiquement réinstallé ;
- Le fichier `apps.json` contient la liste complète de vos logiciels ;
- Vous avez automatisé une installation complète avec une seule commande.

---

## 5️⃣ Bonnes pratiques

- Utiliser l’option `--silent` pour éviter les fenêtres d’installation :
  ```powershell
  winget install 7zip.7zip --silent
  ```

- Mettre à jour la source régulièrement :
  ```powershell
  winget source update
  ```

- Utiliser `export` et `import` pour cloner une configuration entre plusieurs machines.

- Créer des scripts `.ps1` pour automatiser vos installations post-formatage.

---

## 6️⃣ Références utiles

- 📘 Documentation officielle : [https://learn.microsoft.com/windows/package-manager/winget](https://learn.microsoft.com/windows/package-manager/winget)
- 🌐 Catalogue d’applications : [https://winget.run](https://winget.run)
- 💡 Tutoriel complet : [https://learn.microsoft.com/windows/package-manager/winget/](https://learn.microsoft.com/windows/package-manager/winget/)

---

## 🧱 Conclusion
Winget est un outil simple, puissant et officiel pour automatiser vos installations de logiciels Windows.  
En maîtrisant les commandes de base et les fonctions d’export/import, vous pouvez facilement créer vos propres environnements de travail reproductibles et rapides à déployer.
