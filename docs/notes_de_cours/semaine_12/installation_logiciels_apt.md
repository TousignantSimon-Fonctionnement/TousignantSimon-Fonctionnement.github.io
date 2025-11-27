# Installation de logiciels via `apt`

`APT` (Advanced Package Tool) est le système de gestion de paquets par défaut pour les distributions Linux basées sur Debian, comme Ubuntu, Mint, et Debian elle-même. Il simplifie grandement l'installation, la mise à jour, la configuration et la suppression de logiciels.

## Concepts clés d'`APT`

*   **Paquet (Package) :** Un fichier compressé contenant tous les fichiers nécessaires à un programme (exécutables, bibliothèques, documentation) ainsi que des métadonnées sur ses dépendances, sa version, etc.
*   **Dépôt (Repository) :** Un serveur distant qui stocke une collection de paquets logiciels. Votre système Linux est configuré pour interroger ces dépôts afin de trouver et télécharger des logiciels.
*   **Dépendances :** La plupart des logiciels s'appuient sur d'autres logiciels ou bibliothèques pour fonctionner. `APT` gère automatiquement ces dépendances, s'assurant que tous les prérequis sont installés.

## Commandes de base pour l'installation

### 1. Mettre à jour la liste des paquets

Avant toute installation, il est essentiel de mettre à jour votre liste de paquets pour que `APT` connaisse les dernières versions et les nouveaux logiciels disponibles dans les dépôts.

```bash
sudo apt update
```
*(Voir la section "Mise à jour du système Linux" pour plus de détails sur `apt update`.)*

### 2. Rechercher un paquet

Si vous ne connaissez pas le nom exact d'un logiciel ou si vous voulez explorer les options, utilisez `apt search`.

```bash
apt search <mot-clé>
# Exemple : apt search media player
```
Cette commande listera tous les paquets dont la description ou le nom contient le mot-clé spécifié.

### 3. Installer un paquet

Une fois que vous avez trouvé le paquet que vous souhaitez installer, utilisez la commande `apt install`.

```bash
sudo apt install <nom-du-paquet>
# Exemple : sudo apt install vlc
```
-   `sudo` est nécessaire car l'installation de logiciels modifie le système.
-   `APT` vous demandera une confirmation (y/n) avant de télécharger et d'installer le paquet et toutes ses dépendances.

### 4. Installer plusieurs paquets simultanément

Vous pouvez installer plusieurs paquets en les listant simplement les uns après les autres :

```bash
sudo apt install vlc firefox thunderbird
```

### 5. Supprimer un paquet

Pour désinstaller un logiciel sans supprimer ses fichiers de configuration, utilisez `apt remove`.

```bash
sudo apt remove <nom-du-paquet>
# Exemple : sudo apt remove vlc
```

Pour supprimer un paquet **et** ses fichiers de configuration (ce qui est souvent préférable pour un nettoyage complet), utilisez `apt purge`.

```bash
sudo apt purge <nom-du-paquet>
# Exemple : sudo apt purge vlc
```

### 6. Nettoyer les dépendances inutilisées

Après la suppression de logiciels, il peut rester des paquets qui étaient des dépendances et qui ne sont plus nécessaires à aucun autre logiciel. `apt autoremove` les identifie et les supprime.

```bash
sudo apt autoremove
```

## En résumé

L'installation de logiciels avec `apt` est un processus simple et puissant :
1.  `sudo apt update` pour rafraîchir la liste des paquets.
2.  `apt search <mot-clé>` pour trouver des logiciels.
3.  `sudo apt install <nom-du-paquet>` pour installer.
4.  `sudo apt remove <nom-du-paquet>` ou `sudo apt purge <nom-du-paquet>` pour désinstaller.
5.  `sudo apt autoremove` pour nettoyer.