# Laboratoire Semaine 10/11 - Introduction à la ligne de commande Linux

**Objectifs :**
*   Se familiariser avec la navigation dans le système de fichiers.
*   Apprendre à manipuler des fichiers et des répertoires.
*   Utiliser des commandes de base pour obtenir des informations sur le système.
*   S'exercer à utiliser les options des commandes.
*   Découvrir et utiliser `tldr`.

**Prérequis :**
*   Avoir accès à un terminal Linux (soit via une machine virtuelle, un dual boot, ou un service en ligne comme repl.it).
*   Avoir lu les notes de cours de la semaine 10.

---

### Exercice 1 : Navigation

1.  Ouvrez un terminal.
2.  Quelle est la sortie de la commande `pwd` ?
3.  Utilisez `ls -a` pour lister tous les fichiers et répertoires. Que remarquez-vous ?
4.  Créez un répertoire nommé `laboratoire_linux`.
5.  Déplacez-vous dans ce répertoire.
6.  Créez trois sous-répertoires : `documents`, `telechargements`, et `scripts`.
7.  Utilisez `ls -l` pour afficher les détails des répertoires que vous venez de créer.
8.  Naviguez dans le répertoire `documents`.
9.  Revenez au répertoire `laboratoire_linux` en utilisant `cd ..`.

---

### Exercice 2 : Manipulation de fichiers

1.  Dans le répertoire `laboratoire_linux`, créez un fichier vide nommé `mon_fichier.txt` en utilisant la commande `touch mon_fichier.txt`.
2.  Écrivez "Bonjour le monde" dans ce fichier en utilisant la commande `echo "Bonjour le monde" > mon_fichier.txt`.
3.  Affichez le contenu du fichier avec `cat`.
4.  Créez une copie de ce fichier nommée `mon_fichier_copie.txt`.
5.  Renommez `mon_fichier_copie.txt` en `mon_fichier_renomme.txt`.
6.  Déplacez `mon_fichier_renomme.txt` dans le répertoire `documents`.
7.  Créez un fichier caché nommé `.secret.txt` dans `laboratoire_linux`.
8.  Confirmez que le fichier est bien caché en utilisant `ls` et `ls -a`.

---

### Exercice 3 : Exploration du système

1.  Utilisez `tldr` pour en apprendre plus sur la commande `wget`.
2.  Utilisez `wget` pour télécharger une image depuis internet. (par exemple, `wget https://www.linux.org/images/tux-300x354.png`)
3.  Listez les fichiers dans le répertoire `/etc`.
4.  Affichez le contenu du fichier `/etc/os-release` en utilisant `cat`. Quelle distribution de Linux utilisez-vous ?
5.  Utilisez `apt` pour chercher un paquet (par exemple, `apt search htop`).
6.  **(Optionnel, si vous avez les droits sudo)** Installez `htop` en utilisant `sudo apt install htop`. Lancez `htop`. Qu'est-ce que c'est ?

---

### Exercice 4 : Nettoyage

1.  Revenez à votre répertoire `home`.
2.  Supprimez le répertoire `laboratoire_linux` et tout son contenu en utilisant `rm -r laboratoire_linux`. **Soyez très prudent avec cette commande !**