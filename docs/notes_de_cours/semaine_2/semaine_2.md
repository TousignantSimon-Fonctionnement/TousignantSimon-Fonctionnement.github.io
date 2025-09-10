# Personnalisation, Matériel et diagnostique

## 🧹 Désencombrement de Windows 11

La session 2025 m'a donné l'opportunité de changer de matériel — un nouveau portable, fraîchement formaté et réinstallé.

Quelle surprise... J'avais, au fil des années, personnalisé et ajusté mon ancien portable pour le rendre plus fluide et fonctionnel.

Quelle déception de voir la **quantité faramineuse de gadgets, de fenêtres inutiles**, et le **positionnement étrange de certaines fonctionnalités** — souvent redondantes, mal placées, voire inutiles.

---

### 🔍 Fonctions redondantes ou inutiles selon moi

#### 1. La zone de recherche dans la barre des tâches
- **Pourquoi elle est inutile :**  
  Le **menu Windows** (touche `Windows`) permet déjà de faire une recherche immédiate.  
  Il suffit de faire un **petit doigt sur la touche Windows** et de commencer à taper ce que l’on cherche.  
  👉 Pas besoin de bouger la souris jusqu’en bas de l’écran.

#### 2. La météo dans le coin inférieur gauche
- **Pourquoi ?**  
  **Bonne question : pourquoi j'ai ça ?!?**  
  Ce widget est souvent **inutile, distrayant**, voire incorrect. Un clic accidentel dessus t’ouvre une fenêtre MSN pleine de pubs.

#### 3. La position centrée du menu Démarrer
- **Pourquoi :**  
  Ce n’est **pas un problème technique**, mais **une question de préférence**.  
  Personnellement, je trouve **le menu à gauche plus logique**, car il s’aligne avec les habitudes que j’ai prises depuis Windows 95.

![](../../images/personnalisation_barre_taches.png)

## Les notifications.

Souvent windows va vous envoyez des notifications dans la section de droite de votre écran. Généralement, en milieu professionnel, ce sont les courriels, les notifications Teams, etc.

On peut désactiver temporairement les notifications, ou de façon permanente. Voici comment

Désactiver  
![](../../images/personnalisation_barre_tache_notification.png)

Dans le sous-menu pour désactiver temporairement  
![](../../images/personnalisation_barre_tache_notification_desactivation.png)  

Désactiver par application  
![](../../images/personnalisation_notification_autorisation.png)

---

> 💡 **Conclusion :**  
> Le désencombrement de Windows (aussi appelé "debloat") est devenu une étape essentielle pour moi à chaque nouvelle machine.  
> Cela permet de **retrouver un environnement sobre, rapide, et logique** — sans l’enrobage que Microsoft juge utile pour tout le monde.

## Étapes pour réactiver le menu "clique droit complet" 

### Étapes

1. Ouvrez **Invite de commandes** en mode administrateur :  
   - Cliquez sur le menu **Démarrer**, tapez `cmd`,  
   - Faites un clic droit sur **Invite de commandes** et choisissez **Exécuter en tant qu’administrateur**.

2. Copiez-collez la commande suivante et appuyez sur **Entrée** pour appliquer la modification :
  

reg.exe add "HKCU\Software\Classes\CLSID\{86ca1aa0-34aa-4e8b-a509-50c905bae2a2}\InprocServer32" /f /ve


## Qu'est-ce qu'un Éditeur de Registre et à quoi ça sert ?

L’**Éditeur de Registre** (ou **Regedit**) est un outil intégré à Windows qui permet de visualiser, modifier et gérer la base de données centrale du système appelée **Registre Windows**.

### Qu’est-ce que le Registre Windows ?

Le Registre est une immense base de données où Windows et les applications stockent leurs **paramètres de configuration**, **options**, **informations sur le matériel**, ainsi que des données essentielles au fonctionnement du système.

### À quoi sert l’Éditeur de Registre ?

- **Modifier des paramètres système avancés** qui ne sont pas accessibles via les menus classiques.
- **Personnaliser le comportement de Windows** au-delà des options standards.
- **Résoudre des problèmes** en supprimant ou corrigeant des clés erronées.
- **Activer ou désactiver des fonctionnalités cachées**.
- **Gérer les associations de fichiers, les services, les pilotes**, et bien plus.

### Important

L’Éditeur de Registre est un outil puissant, mais **risqué**. **Une modification incorrecte peut entraîner des dysfonctionnements graves, voire empêcher Windows de démarrer.**  

##Langue et internationalisation

## Clavier physique vs Clavier logiciel (layout) sous Windows

### Qu’est-ce que le clavier physique ?  
C’est le clavier matériel réel, celui que vous avez devant vous, avec ses touches physiques (AZERTY, QWERTY, etc.). Par exemple, un clavier **AZERTY français** ou un clavier **QWERTY anglais**.

### Qu’est-ce que le clavier logiciel (layout) ?  
C’est la configuration que Windows utilise pour interpréter les touches que vous tapez.  
Même si vous avez un clavier physique AZERTY, si le layout est réglé sur **Anglais (US)**, les touches n’auront pas le même comportement. Par exemple, taper “A” peut produire un “Q” ou un “@” selon le layout actif.

---

## Comment changer la langue du clavier en Français (Canada) sous Windows  

1. Ouvrez les **Paramètres** (`Windows + I`).  
2. Allez dans **Heure et langue** > **Langue et région**.  
3. Sous **Langues préférées**, cliquez sur **Ajouter une langue** si le français (Canada) n’est pas déjà installé.  
4. Recherchez **Français (Canada)** et installez-le.  
5. Une fois installé, cliquez sur la langue et sélectionnez **Options**.  
6. Sous **Claviers**, assurez-vous que **Français (Canada)** est sélectionné comme clavier.  
7. Pour changer rapidement de clavier pendant que vous tapez, utilisez le raccourci clavier :  
   - `Windows + Espace` pour basculer entre les différentes dispositions.  
   - Ou cliquez sur l’icône de langue dans la barre des tâches (en bas à droite) et choisissez **Français (Canada)**.

---

> **Note importante :**  
> Le clavier physique et le layout logiciel doivent correspondre pour éviter toute confusion. Sinon, les touches ne produiront pas les caractères attendus.


## Matériel
### 
# Les composantes d'un ordinateur, leurs rôles, formats et principales marques

| Composante           | Rôle principal                                                  | Formats / Types courants                  | Principales marques / fabricants         |
|---------------------|----------------------------------------------------------------|------------------------------------------|------------------------------------------|
| **Processeur (CPU)** | Exécute les instructions, réalise les calculs et traite les données | Desktop (LGA 1200, AM4), mobile (BGA)    | Intel (Core i3/i5/i7/i9), AMD (Ryzen)   |
| **Mémoire vive (RAM)** | Stocke temporairement les données et programmes en cours d’utilisation | DDR4, DDR5 (DIMM pour PC, SO-DIMM pour portable) | Corsair, Kingston, Crucial, G.Skill      |
| **Disque dur / SSD** | Stockage permanent des données et du système d’exploitation     | HDD (3,5” pour PC, 2,5” portable), SSD SATA, NVMe M.2 | Western Digital, Seagate, Samsung, Crucial |
| **Carte mère**       | Relie tous les composants et assure la communication entre eux | ATX, Micro-ATX, Mini-ITX                   | ASUS, MSI, Gigabyte, ASRock               |
| **Carte graphique (GPU)** | Traite et génère les images et vidéos affichées à l’écran     | Cartes dédiées (PCIe), GPU intégrés       | NVIDIA (GeForce), AMD (Radeon), Intel (Iris Xe) |
| **Alimentation (PSU)** | Fournit l’énergie électrique nécessaire aux composants          | ATX standard (500W, 650W, 750W, etc.)     | Corsair, Seasonic, EVGA, Be Quiet!       |
| **Système de refroidissement** | Dissipe la chaleur pour éviter la surchauffe                  | Ventilateurs, watercooling, dissipateurs  | Noctua, Cooler Master, Corsair, NZXT     |
| **Périphériques d’entrée** | Permettent à l’utilisateur de communiquer avec l’ordinateur    | Clavier, souris, microphone, scanner       | Logitech, Razer, Microsoft, Corsair      |
| **Périphériques de sortie** | Affichent ou restituent les résultats des traitements          | Écran, imprimante, haut-parleurs           | Dell, LG, BenQ, HP, Bose                  |
| **Carte réseau**     | Connecte l’ordinateur à un réseau local ou internet             | Ethernet (RJ45), Wi-Fi (PCIe, USB)         | Intel, TP-Link, Realtek, ASUS             |
| **BIOS / UEFI**      | Initialise le matériel au démarrage et lance le système         | Firmware intégré sur la carte mère          | AMI, Phoenix, Insyde (OEMs comme ASUS, MSI) |

