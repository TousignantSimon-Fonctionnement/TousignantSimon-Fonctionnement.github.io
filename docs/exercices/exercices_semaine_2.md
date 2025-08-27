# Exercices pratiques pour diagnostiquer et personnaliser un ordinateur sous Windows

## Objectif général  
Développer l’autonomie en utilisant des outils de diagnostic, en exportant un rapport matériel au format CSV, et en personnalisant l’interface Windows.

---

## Exercice 1 : Diagnostiquer son ordinateur avec HWInfo et exporter un rapport CSV

### But  
Utiliser HWInfo pour découvrir les caractéristiques matérielles de votre ordinateur, puis exporter et partager un rapport au format CSV.

### Étapes  
1. Téléchargez et installez **HWInfo** si ce n’est pas déjà fait.  
2. Lancez HWInfo en mode **complet** (pas “Sensors-only” ni “Summary-only”).  
3. Laissez le logiciel analyser votre matériel.  
4. Observez les informations principales :  
   - Modèle du processeur  
   - Quantité de mémoire vive (RAM)  
   - Température actuelle du processeur  
5. Cliquez sur **Rapport** > **Fichier délimité par des virgules (CSV)**.  
6. Enregistrez le fichier sous le nom suivant :  

numéro_da.csv

Remplacez **numéro_da** par votre numéro d’étudiant.  
7. Transmettez ce fichier dans la section devoirs prévue à cet effet (exemple : sur Teams).  
8. Expliquez à un camarade l’utilité de ces données.

---

## Exercice 2 : Personnaliser l’apparence de Windows

### But  
Explorer et modifier les paramètres Windows pour personnaliser votre environnement de travail.

### Étapes  
1. **Changer le fond d’écran**  
- Faites un clic droit sur le bureau, explorez les options et trouvez comment modifier le fond d’écran.  
- Choisissez une image parmi celles proposées ou une photo personnelle.  
- Essayez différents styles d’affichage (remplissage, ajustement, mosaïque, etc.) et notez les différences.

2. **Modifier les couleurs et le thème**  
- Ouvrez les **Paramètres** (`Windows + I`).  
- Allez dans **Personnalisation** > **Couleurs**.  
- Changez entre mode **Clair** et **Sombre**.  
- Sélectionnez une couleur d’accentuation et observez les changements dans l’interface.

3. **Découvrir les paramètres de confidentialité**  
- Dans les **Paramètres** > **Confidentialité et sécurité**, explorez les options liées à :  
  - Historique des activités  
  - Diagnostics et commentaires  
  - Localisation  
- Désactivez celles qui vous semblent inutiles ou intrusives.  

---

## Exercice 3 : Nettoyer son disque dur

### But  
Apprendre à libérer de l’espace en supprimant les fichiers inutiles.

### Étapes  
1. Ouvrez le menu démarrer, tapez **“Nettoyage de disque”** et lancez l’outil.  
2. Sélectionnez le disque système (généralement C:).  
3. Choisissez les catégories de fichiers à supprimer (temporaire, cache, etc.).  
4. Lancez le nettoyage et notez l’espace libéré.  
---


Exercice 4 : Trouver les fichiers et dossiers qui prennent le plus de place

But :
Identifier les éléments les plus volumineux sur votre disque dur à l’aide des outils disponibles dans Windows ou à l’aide d’un utilitaire si vous en avez accès.

---

Étapes :

1. Ouvrez l’explorateur de fichiers (Windows + E).

2. Accédez à votre disque principal :
   Ce PC > Disque local (C:)

3. Explorez les dossiers principaux :
   - Faites un clic droit sur chaque dossier > Propriétés pour afficher la taille.
   - Triez les fichiers d’un dossier par taille pour identifier les plus volumineux.

4. Si vous avez accès à un utilitaire de visualisation (facultatif) :
   Vous pouvez utiliser un outil comme :
   - WinDirStat
   - TreeSize Free
   - SpaceSniffer

   Ces outils permettent de visualiser graphiquement ce qui prend de l’espace.

5. Notez :
   - Le **dossier** le plus volumineux (chemin complet et taille)
   - Le **fichier** le plus volumineux (chemin complet et taille)

6. Nommez le fichier de réponse :
   numero_da.txt  ← remplacez par votre vrai numéro DA

7. Transmettez le fichier texte dans la section **Devoirs** de Teams.

---

Format du fichier à remettre :

---------------------------------------
Numéro DA : [votre numéro]
Nom : [votre nom]

Dossier le plus volumineux :
Chemin : C:\[...\...]
Taille : [ex: 18.2 GB]

Fichier le plus volumineux :
Chemin : C:\[...\...]
Taille : [ex: 6.7 GB]

Outil utilisé : [Explorateur Windows / WinDirStat / TreeSize / SpaceSniffer]

Commentaires :
[Ex. : "Sauvegarde de téléphone", "Jeux", "Film téléchargé", "Fichier système", etc.]
---------------------------------------

⚠️ Ne supprimez rien sans être sûr de son utilité. Demandez à votre enseignant si vous avez un doute.