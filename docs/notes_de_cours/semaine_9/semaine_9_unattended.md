# Cours Windows System Image Manager (WSIM) – Niveau Débutant à Intermédiaire

## 🧭 Objectif du cours
Apprendre à utiliser **Windows System Image Manager (WSIM)** pour créer et gérer des fichiers `autounattend.xml` permettant l’installation automatisée de Windows.

---

## 1️⃣ Introduction à WSIM

### Qu’est-ce que WSIM ?
**WSIM (Windows System Image Manager)** est l’outil officiel fourni par Microsoft pour :
- créer et modifier des fichiers `unattend.xml` ou `autounattend.xml` ;
- automatiser l’installation de Windows ;
- valider la syntaxe et la compatibilité des fichiers de réponses.

### Prérequis
- **Windows Assessment and Deployment Kit (ADK)** installé avec le composant **Deployment Tools** ;
- Une **image Windows (.wim)** correspondant à l’édition que vous souhaitez automatiser ;
- Connaissance basique de Windows et du système de fichiers.

### Vérification de l’installation de WSIM
- WSIM est installé avec l’ADK : recherchez `Windows System Image Manager` dans le menu démarrer.
- Vous pouvez aussi lancer `wsim.exe` depuis `C:\Program Files (x86)\Windows Kits\10\Assessment and Deployment Kit\Deployment Tools\`.

---

## 2️⃣ Concepts clés

| Concept | Description |
|---------|-------------|
| Catalogue (.clg) | Fichier généré par WSIM à partir d’une image .wim, nécessaire pour créer un fichier de réponse. |
| Fichier de réponse (.xml) | Contient toutes les réponses aux questions posées par l’installateur Windows. |
| Composants | Sections du fichier XML correspondant à des phases d’installation (ex. `WindowsPE`, `OfflineServicing`, `Specialize`, `OOBE`). |

---

## 3️⃣ Création d’un projet WSIM

### Étapes de base

1. **Ouvrir WSIM**
   - Lancez `Windows System Image Manager` depuis le menu Démarrer.

2. **Charger l’image Windows (.wim)**
   - `File → Select Windows Image`
   - Sélectionnez le fichier `.wim` de votre installation (ex. `install.wim`).

3. **Créer un catalogue (si nécessaire)**
   - WSIM génère un fichier `.clg` à partir de l’image ; cela peut prendre quelques minutes.

4. **Créer un nouveau fichier de réponse**
   - `File → New Answer File`

5. **Ajouter des composants et paramètres**
   - Exemples : 
     - `WindowsPE → Microsoft-Windows-Setup → UserData → ProductKey`
     - `OOBE → Microsoft-Windows-International-Core → InputLocale`

6. **Valider le fichier**
   - `Tools → Validate Answer File` pour vérifier la syntaxe et la compatibilité.

7. **Enregistrer le fichier**
   - `File → Save Answer File` → nommez-le `autounattend.xml`
   - Placer le fichier à **la racine de votre clé USB d’installation**.

---

## 4️⃣ Laboratoire pratique

### 🎯 Objectif
Créer un fichier `autounattend.xml` simple qui :  
- définit la langue et la disposition du clavier,  
- saisit la clé produit,  
- crée un compte administrateur.

### 🧪 Étapes

1. **Ouvrir WSIM** et charger l’image Windows (`install.wim`).  
2. **Créer un catalogue** si demandé.  
3. **Créer un nouveau fichier de réponse**.  
4. **Ajouter les composants suivants** :  
   - `WindowsPE → Microsoft-Windows-Setup → UserData → ProductKey` : saisissez une clé produit valide.  
   - `WindowsPE → Microsoft-Windows-Setup → UserData → FullName` : saisissez votre nom.  
   - `WindowsPE → Microsoft-Windows-Setup → UserData → Organization` : facultatif.  
   - `WindowsPE → Microsoft-Windows-Setup → ImageInstall → OSImage → InstallFrom` : définissez le chemin de l’image si nécessaire.  
   - `OOBE → Microsoft-Windows-International-Core → InputLocale` et `SystemLocale` : `fr-FR`.  
   - `OOBE → Microsoft-Windows-Shell-Setup → AutoLogon` : créer un compte administrateur.  

5. **Valider le fichier** (`Tools → Validate Answer File`).  
6. **Enregistrer le fichier** : `autounattend.xml` à la racine de la clé USB.  
7. **Tester** en bootant sur la clé USB.

### ✅ Résultat attendu
- Windows s’installe automatiquement avec la configuration définie dans le fichier.  
- Pas d’interaction manuelle nécessaire pour les étapes configurées.  

---

## 5️⃣ Bonnes pratiques

- Toujours **valider** le fichier avec WSIM avant utilisation.  
- Tester dans une **machine virtuelle** avant sur du matériel réel.  
- Sauvegarder votre fichier XML pour réutilisation ou modifications.  
- Utiliser des **composants corrects selon l’édition Windows** (Home, Pro, Enterprise).  
- Éviter de laisser des informations sensibles (mot de passe) en clair dans le fichier pour les environnements partagés.  

---

## 6️⃣ Références utiles

- 📘 Documentation officielle Microsoft : [Unattended Windows Setup Reference](https://learn.microsoft.com/fr-fr/windows-hardware/customize/desktop/unattend/)  
- 📘 Windows ADK : [Télécharger Windows ADK](https://learn.microsoft.com/fr-fr/windows-hardware/get-started/adk-install)  
- 🌐 Tutoriel WSIM complet : [WSIM Step-by-Step Guide](https://learn.microsoft.com/en-us/windows-hardware/customize/desktop/wsim/)  

---

## 🧱 Conclusion
Windows System Image Manager est l’outil officiel pour automatiser les installations Windows avec des fichiers `autounattend.xml`.  
En maîtrisant WSIM, vous pouvez créer des déploiements rapides, reproductibles et personnalisés pour vos postes.