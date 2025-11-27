# Utilitaires

## Baobab (Analyseur d'utilisation de disque / Disk Usage Analyzer)
Baobab est une application graphique conviviale pour analyser l'utilisation de l'espace disque. Elle vous permet de visualiser rapidement quels fichiers et dossiers occupent le plus d'espace sur votre système.

*   **Fonctionnalité :** Affiche une représentation visuelle (souvent un graphique en anneau ou en arbre) de l'espace disque utilisé, facilitant l'identification des "mangeurs" d'espace.
*   **Utilisation :** Généralement lancée depuis le menu des applications de votre environnement de bureau ou via la commande `baobab` dans le terminal.
*   **Avantages :** Très intuitif, aide à libérer de l'espace disque en repérant les gros fichiers/dossiers.

## gparted (Gestionnaire de partitions de disque)
gparted est un éditeur de partitions graphique. Il est utilisé pour créer, supprimer, redimensionner, déplacer, vérifier et copier des partitions de disque.

*   **Fonctionnalité :** Permet de gérer les partitions de vos disques durs (créer de nouvelles partitions pour Linux, redimensionner une partition Windows existante, etc.).
*   **Utilisation :** Souvent utilisé avant ou pendant l'installation de systèmes d'exploitation multiples (dual-boot) ou pour préparer de nouveaux disques.
*   **Attention :** C'est un outil très puissant qui, mal utilisé, peut entraîner une perte de données. Toujours sauvegarder vos données avant d'effectuer des opérations avec `gparted`.

## htop (Moniteur de processus interactif)
`htop` est un moniteur de processus interactif et un visualiseur de tâches pour les systèmes Linux. C'est une alternative plus conviviale et plus riche en fonctionnalités que la commande `top`.

*   **Fonctionnalité :** Affiche une liste dynamique des processus en cours d'exécution, l'utilisation du CPU, de la mémoire et du swap. Il permet de trier, filtrer et envoyer des signaux aux processus (par exemple, pour les arrêter).
*   **Utilisation :** Lancez-le en tapant `htop` dans le terminal.
*   **Avantages :** Interface colorée et interactive, facile à naviguer avec la souris ou les flèches du clavier. Idéal pour diagnostiquer les performances système et gérer les processus.

## `lsblk` (Lister les périphériques bloc)
La commande `lsblk` (list block devices) liste les périphériques bloc (disques durs, SSD, clés USB, etc.) et leurs partitions.

*   **Fonctionnalité :** Fournit une vue arborescente des périphériques de stockage, montrant leur taille, leur point de montage et leur type.
*   **Exemple :**
    ```bash
    lsblk
    # Exemple de sortie :
    # NAME        MAJ:MIN RM   SIZE RO TYPE MOUNTPOINTS
    # sda           8:0    0   100G  0 disk
    # ├─sda1        8:1    0    50G  0 part /
    # ├─sda2        8:2    0     4G  0 part [SWAP]
    # └─sda3        8:3    0    46G  0 part /home
    # sdb           8:16   1    16G  0 disk
    # └─sdb1        8:17   1    16G  0 part /media/usb
    ```
*   **Utilité :** Très utile pour comprendre la structure de vos disques et partitions, et identifier les noms de périphériques (comme `/dev/sda` ou `/dev/sdb`) avant de les utiliser avec d'autres commandes.

## `du -s` (Disk Usage - Summary)
La commande `du` (disk usage) est utilisée pour estimer l'espace disque utilisé par les fichiers et les répertoires. L'option `-s` (summary) affiche seulement le total pour chaque argument.

*   **Fonctionnalité :** Calcule et affiche l'espace total occupé par un répertoire ou un fichier spécifié.
*   **Exemple :**
    ```bash
    du -sh mon_projet/
    # Affiche la taille totale du répertoire 'mon_projet/' de manière lisible par l'homme.
    # Exemple de sortie : 2.5G    mon_projet/
    ```
    ```bash
    du -sh *
    # Affiche la taille de chaque fichier et dossier dans le répertoire courant.
    ```
*   **Utilité :** Rapidement identifier les répertoires qui consomment beaucoup d'espace disque. Le `-h` est souvent utilisé avec `-s` pour une sortie "human-readable".
