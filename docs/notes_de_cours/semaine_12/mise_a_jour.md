# Mise à jour du système Linux

Maintenir son système Linux à jour est crucial pour la sécurité, la stabilité et l'accès aux dernières fonctionnalités. Sous les distributions basées sur Debian (comme Ubuntu), cela se fait principalement via le gestionnaire de paquets `APT` (Advanced Package Tool).

Il y a généralement deux étapes principales pour mettre à jour votre système :

## 1. Mettre à jour la liste des paquets (apt update)

La première étape consiste à récupérer la liste la plus récente des paquets disponibles depuis les dépôts. Cette commande ne met pas à jour les logiciels installés, elle met juste à jour la "carte" de ce qui est disponible.

```bash
sudo apt update
```
-   `sudo` : Nécessaire car cette opération modifie les informations système.
-   `apt update` : Récupère les informations sur les nouvelles versions des paquets et leurs dépendances. Vous verrez souvent des informations sur le nombre de paquets qui peuvent être mis à jour.

## 2. Mettre à niveau les paquets installés (apt upgrade)

Une fois que votre système connaît les dernières versions des paquets, vous pouvez procéder à la mise à niveau des logiciels installés.

```bash
sudo apt upgrade
```
-   `sudo` : Encore une fois, nécessaire car cette commande modifie les fichiers du système en remplaçant les anciennes versions des logiciels par les nouvelles.
-   `apt upgrade` : Installe les nouvelles versions de tous les paquets que vous avez déjà installés sur votre système. Il gère intelligemment les dépendances pour s'assurer que tout fonctionne correctement.

### Mettre à jour et mettre à niveau en une seule commande

Il est courant de combiner les deux commandes :

```bash
sudo apt update && sudo apt upgrade
```
Le `&&` signifie que la deuxième commande (`sudo apt upgrade`) ne s'exécutera que si la première (`sudo apt update`) s'est terminée avec succès.

## Nettoyage (apt autoremove)

Après des mises à jour, il arrive que des paquets "dépendances" qui n'étaient nécessaires que pour d'anciennes versions de logiciels restent sur le système. Vous pouvez les supprimer pour libérer de l'espace :

```bash
sudo apt autoremove
```

## Mise à niveau majeure de la distribution (dist-upgrade)

Pour passer à une nouvelle version majeure de votre distribution (par exemple, d'Ubuntu 20.04 à 22.04), vous utiliseriez généralement :

```bash
sudo apt dist-upgrade
```
Ou, pour Ubuntu spécifiquement :
```bash
sudo do-release-upgrade
```
Ceci est une opération plus complexe et doit être faite avec précaution, après avoir sauvegardé vos données importantes.

En résumé, pour une maintenance régulière, les commandes `sudo apt update && sudo apt upgrade` suivies de `sudo apt autoremove` sont vos meilleures amies.