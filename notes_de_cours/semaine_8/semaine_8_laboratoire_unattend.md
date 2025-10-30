# Laboratoire – Installation de Windows sans intervention  
## Objectif  
Dans ce laboratoire, vous devez installer Windows 11 (ou Windows 10) de façon **totalement automatisée**, sans intervention utilisateur pendant l’installation (pas de fenêtres interactives).  
## Indice utile  
Pour générer le fichier de réponse (`autounattend.xml`) qui permettra l’installation sans interaction, utilisez l’outil en ligne suivant :  
[Generate autounattend.xml files for Windows 10/11](https://schneegans.de/windows/unattend-generator/)  
L’outil permet de configurer :  
- les paramètres régionaux, langue et clavier. :contentReference[oaicite:2]{index=2}  
- le partitionnement et le formatage du disque. :contentReference[oaicite:3]{index=3}  
- la sélection de l’édition de Windows et la clé produit. :contentReference[oaicite:4]{index=4}  
- de masquer toute fenêtre PowerShell pendant l’installation. :contentReference[oaicite:5]{index=5}  
## Consignes  
1. Téléchargez ou préparez votre image d’installation de Windows.  
2. Utilisez l’outil ci‑dessus pour générer un fichier `autounattend.xml` adapté à votre machine.  
3. Placez ce fichier à la racine du support d’installation USB (ou dans Windows PE selon votre procédure).  
4. Lancez l’installation de Windows, et vérifiez qu’il n’y a **aucune intervention demandée** (pas de dialogues, pas de configuration manuelle).  
5. Une fois l’installation terminée, assurez‑vous que le système fonctionne correctement (langue, clavier, réseau, compte utilisateur, etc.).  
## À remettre  
- Le fichier Word tel que défini en classe 

Bonne réussite !  