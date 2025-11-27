# Semaine 10 - Introduction à Linux

Cette semaine, nous allons explorer les bases de Linux et de sa ligne de commande.

## Commandes de base

### `ls` - Lister les fichiers
La commande `ls` permet de lister les fichiers et les répertoires.

- `ls -l`: Affiche une liste détaillée.
- `ls -a`: Affiche tous les fichiers, y compris les fichiers cachés.
- `ls -h`: Affiche les tailles de fichiers de manière lisible pour l'homme (par exemple, 1K, 2M, 3G).

On peut combiner ces options:
```bash
ls -lah
```

### `mkdir` - Créer un répertoire
La commande `mkdir` permet de créer un nouveau répertoire.
```bash
mkdir mon_nouveau_dossier
```

### `cd` - Changer de répertoire
La commande `cd` (change directory) permet de se déplacer dans l'arborescence des fichiers.
```bash
cd mon_nouveau_dossier
```

### `cat` - Afficher le contenu d'un fichier
La commande `cat` permet d'afficher le contenu d'un fichier texte dans le terminal.
```bash
cat mon_fichier.txt
```

### `pwd` - Afficher le répertoire courant
La commande `pwd` (print working directory) affiche le chemin complet du répertoire dans lequel vous vous trouvez.

```bash
pwd
```

## Commandes de manipulation de fichiers

### `touch` - Créer un fichier vide
La commande `touch` permet de créer un fichier vide. Si le fichier existe déjà, la commande mettra à jour sa date de dernière modification.
```bash
touch mon_fichier.txt
```

### `echo` - Afficher du texte et rediriger la sortie
La commande `echo` affiche le texte que vous lui donnez. On peut utiliser le symbole `>` pour rediriger cette sortie vers un fichier (écrasant son contenu) ou `>>` pour l'ajouter à la fin du fichier.
```bash
echo "Bonjour le monde" > mon_fichier.txt
```

### `cp` - Copier des fichiers et des répertoires
La commande `cp` (copy) permet de copier des fichiers et des répertoires.

- Pour copier un fichier dans le même répertoire :
  ```bash
  cp rapport_final.txt rapport_final_v2.txt
  ```
- Pour copier un fichier dans un autre répertoire :
  ```bash
  cp photo_de_vacances.jpg /home/user/images/
  ```
- Pour copier un répertoire entier et son contenu, on utilise l'option `-r` (récursif) :
  ```bash
  # Crée une sauvegarde complète de votre projet
  cp -r mon_projet/ /media/usb/sauvegarde_projet/
  ```

### `mv` - Déplacer ou renommer des fichiers
La commande `mv` (move) permet de déplacer un fichier ou de le renommer.
```bash
mv mon_fichier.txt mon_nouveau_nom.txt # Renomme
mv mon_nouveau_nom.txt ../ # Déplace dans le dossier parent
```

### `rm` - Supprimer des fichiers
La commande `rm` (remove) permet de supprimer des fichiers. Pour supprimer un répertoire et tout son contenu, on utilise l'option `-r` (récursif). **Attention, cette commande est irréversible !**
```bash
rm mon_fichier.txt
rm -r mon_dossier
```

## Recherche de fichiers et de texte

### `find` - Trouver des fichiers et des répertoires
La commande `find` est un outil de recherche puissant. Elle permet de trouver des fichiers en se basant sur leur nom, leur taille, leur date de modification, etc.

- Pour trouver tous les fichiers qui se terminent par `.log` dans votre dossier personnel :
  ```bash
  find /home/user -name "*.log"
  ```
- Pour trouver tous les répertoires modifiés dans les dernières 24 heures :
  ```bash
  find . -type d -mtime -1
  ```
- Pour trouver tous les fichiers de plus de 100 Mo et les lister en détail :
  ```bash
  find / -type f -size +100M -exec ls -lh {} \;
  ```
  Cet exemple exécute la commande `ls -lh` sur chaque fichier trouvé.

### `grep` - Chercher du texte dans des fichiers
La commande `grep` (Global Regular Expression Print) permet de chercher une chaîne de caractères ou une expression régulière dans un ou plusieurs fichiers.

- Pour chercher le mot "erreur" dans un fichier de log :
  ```bash
  grep "erreur" /var/log/syslog
  ```
- Pour chercher une adresse IP dans les logs d'un serveur web, en ignorant la casse :
  ```bash
  grep -i "192.168.1.100" /var/log/apache2/access.log
  ```
- Pour compter le nombre de fois où une fonction est appelée dans votre code source (en cherchant son nom) :
  ```bash
  grep -c "maFonctionSuperImportante" *.js
  ```
- En combinaison avec `find`, pour chercher un texte dans tous les fichiers `.md` du répertoire courant :
  ```bash
  find . -name "*.md" -exec grep "Linux" {} \;
  ```

## Notions de base

### Fichiers cachés
Sous Linux, les fichiers et répertoires dont le nom commence par un point (`.`) sont des fichiers cachés. Ils ne sont pas affichés par défaut par la commande `ls`. Pour les voir, il faut utiliser l'option `-a`.

### Dossiers spéciaux
- `.` : Représente le répertoire courant.
- `..` : Représente le répertoire parent.

### Dossiers généraux
- `/etc`: Contient les fichiers de configuration du système.
- `/dev`: Contient les fichiers de périphériques.
- `/home`: Contient les dossiers personnels des utilisateurs.

## Gestion des paquets avec `apt`
`apt` est un gestionnaire de paquets utilisé par les distributions basées sur Debian (comme Ubuntu).

- `apt update`: Met à jour la liste des paquets disponibles.
- `apt upgrade`: Met à jour tous les paquets installés vers leurs dernières versions.
- `apt search <terme>`: Recherche un paquet dans les dépôts.
- `apt install <nom_du_paquet>`: Installe un nouveau paquet.
- `apt remove <nom_du_paquet>`: Supprime un paquet.

## Permissions et `sudo`
Certaines commandes, notamment celles qui affectent le système (comme l'installation de logiciels), nécessitent des privilèges d'administrateur. La commande `sudo` (superuser do) permet d'exécuter une commande en tant qu'administrateur.
```bash
sudo apt install htop
```

## Utilitaires

### `wget`
`wget` est un utilitaire en ligne de commande pour télécharger des fichiers depuis le web.
```bash
wget https://une.url.com/un_fichier_a_telecharger.zip
```

### `tldr`
`tldr` est un outil qui simplifie les pages `man` (manuel) en fournissant des exemples pratiques pour les commandes les plus courantes.

Pour l'installer, vous pouvez utiliser `apt`:
```bash
sudo apt install tldr
```
Ensuite, vous pouvez l'utiliser comme ceci:
```bash
tldr ls
```

### `htop`
`htop` est un moniteur de processus interactif. C'est une version améliorée de la commande `top`. Il permet de voir en temps réel les processus en cours, l'utilisation du CPU et de la mémoire.
