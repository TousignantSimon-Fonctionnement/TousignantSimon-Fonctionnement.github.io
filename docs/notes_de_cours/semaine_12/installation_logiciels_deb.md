# Installation de logiciels via les fichiers `.deb`

Sous les distributions basées sur Debian (comme Ubuntu), les fichiers `.deb` sont des paquets logiciels autonomes qui contiennent tous les éléments nécessaires à l'installation d'une application. Bien que `APT` soit le moyen privilégié d'installer des logiciels depuis les dépôts, il arrive que vous deviez installer un fichier `.deb` téléchargé manuellement (par exemple, pour une application qui n'est pas dans les dépôts officiels, ou une version plus récente que celle disponible via `APT`).

## Qu'est-ce qu'un fichier `.deb` ?

Un fichier `.deb` est l'équivalent sous Debian/Ubuntu d'un fichier `.exe` sous Windows ou `.dmg` sous macOS. C'est un format de paquet standard qui permet l'installation d'un logiciel via un double-clic ou une commande en ligne.

## Méthodes d'installation

Il existe plusieurs façons d'installer un fichier `.deb` :

### 1. Installation graphique (la plus simple)

La plupart des environnements de bureau Linux sont configurés pour ouvrir les fichiers `.deb` avec un "Installateur de paquets" graphique (comme le Logiciel Ubuntu, GDebi, etc.).

*   **Étapes :**
    1.  Téléchargez le fichier `.deb` (par exemple, depuis le site officiel de l'application).
    2.  Naviguez jusqu'à l'emplacement du fichier dans votre gestionnaire de fichiers.
    3.  Double-cliquez sur le fichier `.deb`.
    4.  L'installateur de paquets s'ouvrira, vous montrera les détails du logiciel et vous proposera un bouton "Installer".
    5.  Cliquez sur "Installer" et entrez votre mot de passe lorsque demandé.

### 2. Installation via la ligne de commande avec `dpkg`

`dpkg` est l'outil de bas niveau utilisé par `APT` pour installer, supprimer et gérer les paquets `.deb`. Vous pouvez l'utiliser directement.

*   **Syntaxe :**
    ```bash
    sudo dpkg -i nom_du_paquet.deb
    ```
    -   `sudo` : Nécessaire car l'installation modifie le système.
    -   `dpkg` : La commande elle-même.
    -   `-i` (ou `--install`) : Indique à `dpkg` d'installer le paquet.
    -   `nom_du_paquet.deb` : Le chemin complet vers votre fichier `.deb`.

*   **Exemple :**
    ```bash
    cd ~/Téléchargements
    sudo dpkg -i google-chrome-stable_current_amd64.deb
    ```

#### Gestion des dépendances avec `dpkg`

Un inconvénient majeur de `dpkg` seul est qu'il ne gère pas automatiquement les dépendances. Si le paquet `.deb` que vous installez nécessite d'autres paquets qui ne sont pas déjà installés, `dpkg` échouera en signalant des erreurs de dépendances.

Pour résoudre ce problème, vous pouvez utiliser `apt --fix-broken install` après une tentative d'installation avec `dpkg` :

```bash
sudo dpkg -i mon_logiciel.deb # Cette commande peut échouer à cause des dépendances
sudo apt --fix-broken install # Cette commande va télécharger et installer les dépendances manquantes
```

### 3. Installation via la ligne de commande avec `apt` (recommandé)

Depuis Ubuntu 14.04 (et versions ultérieures de Debian), vous pouvez utiliser `apt` directement pour installer les fichiers `.deb` locaux. Cette méthode est recommandée car `apt` gère automatiquement les dépendances !

*   **Syntaxe :**
    ```bash
    sudo apt install ./nom_du_paquet.deb
    ```
    -   `./` : Le préfixe `./` est **crucial**. Il indique à `apt` que le paquet est un fichier local et non un paquet à rechercher dans les dépôts.

*   **Exemple :**
    ```bash
    cd ~/Téléchargements
    sudo apt install ./google-chrome-stable_current_amd64.deb
    ```
    `apt` va alors analyser le fichier `.deb`, identifier ses dépendances et les installer automatiquement si nécessaire.

## Désinstallation d'un paquet installé via `.deb`

Que vous ayez installé le paquet via l'interface graphique, `dpkg` ou `apt`, la désinstallation se fait de la même manière qu'un paquet standard, en utilisant `apt remove` ou `apt purge` avec le nom du paquet (pas le nom du fichier `.deb`).

```bash
sudo apt remove google-chrome-stable
# ou pour supprimer les fichiers de configuration également
sudo apt purge google-chrome-stable
```

En utilisant `sudo apt install ./mon_fichier.deb`, vous combinez la simplicité de `dpkg` pour les fichiers locaux avec la gestion robuste des dépendances d'`apt`.