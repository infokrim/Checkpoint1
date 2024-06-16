# **</ins>  exercice 3 </ins>**
---

### 1. :arrow_down_small: :arrow_down_small: :arrow_down_small:
`cut -d: -f1 /etc/passwd`

### 2. :arrow_down_small: :arrow_down_small: :arrow_down_small:
Commande :`Chmod 744 myfile`   

### 3. :arrow_down_small: :arrow_down_small: :arrow_down_small:
Créer un nouveau fichier nommé .gitignore à la racine du Git (peut être fait en ligne de commande `touch .gitignore`.  
Puis la commande `echo '*.pdf' >> .gitignore` ajoute une ligne au fichier .gitignore qui indique à Git d'ignorer tous les fichiers avec l'extension **pdf**.   
   
### 4. :arrow_down_small: :arrow_down_small: :arrow_down_small:
Il faut vérifier qu'on est sur la branche main avec la commande `git checkout main` pour fusionner la branche "test_valide" dans "main" avec la commande `git merge test_valide`   

### 5. :arrow_down_small: :arrow_down_small: :arrow_down_small:
echo -e 'Malgré le prix élevé de 100$, il a dit "Bonjour !" au vendeur :\n- "Bonjour est-ce que ce clavier fonctionne bien ?" \n- "Evidemment ! On peut tout écrire avec, que ce soit des pipe | ou bien des backslash \\\\ !" \n- "Même des tildes ~ ?" \n- "Evidemment !"'   

### 6. :arrow_down_small: :arrow_down_small: :arrow_down_small:
La commande : `ps -C gedit`   

### 7. :arrow_down_small: :arrow_down_small: :arrow_down_small:

**a. Pour la couche 2 (liaison de données), il y a comme matériels :**
    
**a. Commutateur (Switch) :** 
- Permet de connecter et commuter des trames Ethernet entre différents ports
- Utilise les adresses MAC pour aiguiller le trafic
- Crée des segments de collision séparés
**b. Pont (Bridge) :**	
- Interconnecte des segments de réseau local (LAN)   
- Filtre et transmet les trames Ethernet en fonction des adresses MAC   
- Apprend dynamiquement les adresses MAC connectées à chaque port   
		
**b. Pour la couche 3 (Réseau), il y a comme matériels :**

**a. Routeur :**   
- Interconnecte des réseaux différents (LAN, WAN, Internet, etc.)   
- Utilise les adresses IP pour aiguiller le trafic entre les réseaux  
- Effectue le routage des paquets IP en fonction des tables de routage
- Peut également offrir des fonctions de pare-feu et de traduction d'adresses (NAT)   
		 
**b. Passerelle (Gateway) :**
- Permet d'interconnecter des réseaux utilisant des protocoles différents
- Fait office de point d'entrée/sortie entre deux réseaux hétérogènes   
- Effectue la conversion et la traduction des données entre les protocoles   

### 8. :arrow_down_small: :arrow_down_small: :arrow_down_small:
Équivalents PowerShell des commandes bash

- **cd en Bash : Set-Location (cd fonctionne aussi en PowerShell)**    
- **cp en Bash : Copy-Item**    
- **mkdir en Bash : New-Item -ItemType Directory**    
- **ls en Bash : Get-ChildItem (ls fonctionne aussi en PowerShell)**   	

### 9. :arrow_down_small: :arrow_down_small: :arrow_down_small:

**Payload :** Le payload dans une trame Ethernet est la section qui contient les données réelles à transmettre.  
C'est l'information utile véhiculée par la trame, excluant les en-têtes Ethernet et les informations de contrôle.  
Elle peut inclure des segments de données provenant des couches supérieures du modèle OSI.  

### 10. :arrow_down_small: :arrow_down_small: :arrow_down_small:

Remplacement des classes IP par le CIDR: Le CIDR (Classless Inter-Domain Routing)  
Avec le système par classes, l'attribution des adresses IP était très limitée et provoquait un gaspillage important de l'espace d'adressage.  
Le CIDR permet une attribution plus flexible et efficace des adresses IP en utilisant des masques de sous-réseaux.
Le CIDR a rendu obsolète la notion de classes d'adresses IP, permettant une gestion plus efficace de l'espace d'adressage IPv4.


	  


