
# **<ins>Exercice 1 - Gestion du stockage</ins>**
---


###  <ins>**1.1 Préparation du disque 2**</ins>

####        **a. Première étape : création des partitions**  
####            **- Première partition de 6Go**  

"lsblk" est un programme qui affiche les différents périphériques de la VM (virtual machine).  
Taper `lsblk`  


**la fenêtre suivante s'affiche :**  


![](https://github.com/infokrim/Checkpoint1/blob/main/exercice1/Partie%201/image1.PNG)


Le second disque est **sdb**.


**Commandes pour partitionnement :**

`Cfdisk /dev/sdb`  


**"cfdisk"** est un programme de manipulation de tables de partitions.  
**"/dev/sdb"** est le disque sur lequel il faut créer deux partitions.  
                 
**la fenêtre suivante s'affiche :**  

![](https://github.com/infokrim/Checkpoint1/blob/main/exercice1/Partie%201/image2b.PNG)


Choisir **Dos** pour le type de partition demandé.  
                  
                  
**la fenêtre suivante s'affiche :**  


![](https://github.com/infokrim/Checkpoint1/blob/main/exercice1/Partie%201/image3.PNG)
                 
                 
Le disque **"sdb"** est affiché comme espace libre (donc non partitionné) et indique une taille de 10 Go.  

Choisir **"Nouvelle"** (appuyer sur la touche n).

**la fenêtre suivante s'affiche :**  


![](https://github.com/infokrim/Checkpoint1/blob/main/exercice1/Partie%201/image4.PNG)


Donner la taille de 6Go à la partition désirée (remplacer 10G par 6G) et appuyer sur entrée.


 **la fenêtre suivante s'affiche :**  



 ![](https://github.com/infokrim/Checkpoint1/blob/main/exercice1/Partie%201/image5.PNG)
                 
                 
                 
Choisir **partition primaire** pour le type demandé


**la fenêtre suivante s'affiche :**  


![](https://github.com/infokrim/Checkpoint1/blob/main/exercice1/Partie%201/image6.PNG)
                 
                 
**la fenêtre suivante s'affiche :**  
                 
                 
![](https://github.com/infokrim/Checkpoint1/blob/main/exercice1/Partie%201/image7.PNG)
                  
                 
Le type de la partition apparait en bas au dessus des options, "Linux (83)" pour partition linux (définit par défaut)

                 
![](https://github.com/infokrim/Checkpoint1/blob/main/exercice1/Partie%201/image7b.PNG)
                   
  
  
####            **- Deuxième partition (SWAP)**  
                
Sur le disque "sdb", il reste un espace libre de 4 Go.
                
                
![](https://github.com/infokrim/Checkpoint1/blob/main/exercice1/Partie%201/image7bb.PNG)
              
                
                             
4 Go sera la taille de la deuxième partition "SWAP".
                
                
![](https://github.com/infokrim/Checkpoint1/blob/main/exercice1/Partie%201/image8.PNG)
                      
                
                
 Toujours dans le programme cfdisk, choisir l'action "Nouvelle".
 Pour cela avec la flèche du bas(du clavier), se positionner sur "esapce libre"  
 Appuyer sur la touche n (ou se positionner sur "Nouvelle" avec la flèche gauche du clavier, puis appuyer sur la touche "entrée").  
                
 Laisser la taille de partition à **4Go** (4G espace libre restant affiché).  
                
![](https://github.com/infokrim/Checkpoint1/blob/main/exercice1/Partie%201/image9.PNG)

                
Choisir Primaire, pour le type de partition

  ![](https://github.com/infokrim/Checkpoint1/blob/main/exercice1/Partie%201/image10.PNG)
  
                
**la fenêtre suivante s'affiche :**  
                
                
 ![](https://github.com/infokrim/Checkpoint1/blob/main/exercice1/Partie%201/image11.PNG)
                
Appuyer sur la touche T (comme type), (ou se positionner sur "Type" en navigant avec les flèches gauche et droite du clavier, puis appuyer sur la touche "entrée").  
                
                
**la fenêtre suivante s'affiche :**  
                
                
![](https://github.com/infokrim/Checkpoint1/blob/main/exercice1/Partie%201/image12.PNG)

Pour choisir le type de partition SWAP, se positionner sur **"82 partition d’échange Linux/Solaris"**  
                
**la fenêtre suivante s'affiche :**  
                
                
![](https://github.com/infokrim/Checkpoint1/blob/main/exercice1/Partie%201/image13.PNG)
                
                
 Le disque **"sdb"** est maintenant divisé en deux partitions.  
**Une partition "sdb1" de type "linux" d'une taille de 6 Go.**   
**Une partition "sdb2" de type "partition d’échange Linux/Solaris" d'une taille de 4 Go.**   
                
                
:warning: Il faut écrire les partitions du disque crées pour qu'elles soient crées réellement.  
                
Séléctionner "Ecrire" puis appuyer sur la touche "Entrée"(ou appuyer sur la touche E du clavier) pour enregistrer les partitions créées. 

                
![]( https://github.com/infokrim/Checkpoint1/blob/main/exercice1/Partie%201/image13b.PNG)
                                
                
 **la fenêtre suivante s'affiche :** 
                
                
 ![]( https://github.com/infokrim/Checkpoint1/blob/main/exercice1/Partie%201/image14.PNG)


Taper le mot **"oui"** puis appuyer sur la touche "Entrée" pour effectuer l'écriture des partitions sur le disque.  
                
                
![](https://github.com/infokrim/Checkpoint1/blob/main/exercice1/Partie%201/image14bb.PNG)
                
![](https://github.com/infokrim/Checkpoint1/blob/main/exercice1/Partie%201/image14b2.PNG)  
                
"La table de partitions a été altérée." (en bleu sur l'image du dessus) indique que l'écriture des partitions est effective.   
                
                
Quitter le programme en appuyant sur la touche "Q" du clavier 
                
**la fenêtre suivante s'affiche :**  
                
La commande "clear" permet de nettoyer l'écran pour la deuxième partie de l'exercice.  

---
                
                
                
####        **b. Deuxième étape : Formatage des partitions crées**  


**- disque sdb1**
                
Taper la commande "lsblk" pour afficher l'arborescence des disques
                
`lsblk`
                
                
**la fenêtre suivante s'affiche :**  
                
![](https://github.com/infokrim/Checkpoint1/blob/main/exercice1/Partie%202/image1.PNG)
                
Les deux partitions crées avant (**sdb1** et sdb2**) doivent être maintenant formatées.
                
**Formatage de la partition sdb1**  
                
Taper la ligne de commande suivante :   
                
**`mkfs.ext4 -L DATA /dev/sdb1`**  
                
**`mkfs.ext4`** formate la partition en ext4.   
                
**`-L DATA`** donne le nom DATA à la partition formatée.  
                
**`/dev/sdb1`** correspond à la partition à formater.  
                
![](https://github.com/infokrim/Checkpoint1/blob/main/exercice1/Partie%202/image2.PNG)

                
Les mots "done" sur les différentes lignes affichées (étapes du formatage) indiquent que l'opération s'est bien passée.    
Pour avoir la preuve, la commande "lsblk" suivie de l'option "-f" permet d'afficher plus de détails sur less périphériques.   
                
                
Taper la commande suivante : 
                
`lsblk -f`  
                
                
![](https://github.com/infokrim/Checkpoint1/blob/main/exercice1/Partie%202/image3.PNG)
                
                             
                               
La colonne "FSTYPE" indique le type **"ext4"** et la colonne **"LABEL"** indique le nom **"DATA"**  pour **"sdb1"**.  
                
                
**Formatage de la partition sdb2**   
                
                
Taper la commande suivante : 
                
                
`mkswap /dev/sdb2`
                
                
Cette commande crée une zone d'échange Linux sur le périphérique "/dev/sdb2".  
                
Pour activer la partition "sdb2" utiliser la commande "swapon"   
                

`swapon /dev/sdb2`  
                
                
"swapon" est utilisé pour indiquer les périphériques sur lesquels la pagination et l'échange auront lieu.
" /dev/sdb2" indique la partition a activer en swap.   
![](https://github.com/infokrim/Checkpoint1/blob/main/exercice1/Partie%202/image4.PNG)
                   
                
Quand on tape la commande "lsblk", on remarque qu'une partition "SWAP" est déjà crée sur la partition "sda5".  
                
                
![](https://github.com/infokrim/Checkpoint1/blob/main/exercice1/Partie%202/image5.PNG)                                 
                 
Il est possible d'avoir plusieurs partitions SWAP sur une machine, mais une seule partition SWAP suffit.  
                
Pour désactiver la partition "SWAP" existante sur  sda 5, taper la commande suivante :       
                
`swapoff /dev/sda5`  
                
![](https://github.com/infokrim/Checkpoint1/blob/main/exercice1/Partie%202/image6.PNG)


puis taper  
                
                
 `lsblk `  
                
                
![](https://github.com/infokrim/Checkpoint1/blob/main/exercice1/Partie%202/image7.PNG)

**"sdb2"** est maintenant la seule partition d'échange "SWAP".  
                 
                 
###  <ins>**1.2 Montage**</ins>**   

         
**Création des dossiers pour le montage des partitions**  
                
Création des dossier de montage pour la partition DATA  
Liste de commandes :   
                
 ```
cd /
ls
mkdir /mnt/data
ls data
 ```
                
                
`cd /` se positionner dans le dossier racine (root).   
`ls` liste les dossiers et fichiers du répertoire courant (ici répertoire root).   
`mkdir /mnt/data` créer le dossier "data" dans le dossier "/mnt".   
`cd mnt` se positionner dans le dossier mnt (/mnt est le répertoire utilisé pour monter temporairement un système de fichiers.   
`ls` liste les dossiers et fichiers du répertoire courant.   
`ls data` vérification contenu dossier data (normalement vide puisque nouvellement crée).   

                
![](https://github.com/infokrim/Checkpoint1/blob/main/exercice1/Partie%202/image10.PNG)
                
                
                
**Montage du dossier data**
                
Taper la commande :   
                
**`mount -t ext4 /dev/sdb1 /mnt/data`**   
               
                
                
`mount` : La commande mount est utilisée pour monter un système de fichiers (comme une partition) sur un répertoire spécifié.   
                
                
`-t ext4 ` : L’option "-t" spécifie le type de système de fichiers. Dans ce cas, nous utilisons ext4.   
                
                
`/dev/sdb1` : C’est le périphérique (ou la partition) que nous voulons monter. /dev/sdb1 fait référence à la première partition du disque "sdb".  
                
                
`/mnt/data` : C’est le répertoire de montage. Une fois la partition montée, son contenu sera accessible via ce répertoire.  
                
                
puis taper  
                
                
 `lsblk `  
                
                
![](https://github.com/infokrim/Checkpoint1/blob/main/exercice1/Partie%202/image11.PNG)
                
                
La partition **"sdb1"** est bien montée dans le répertoire de montage **"/mnt/data"**.   
                
                
                
**Montage automatique de la partition DATA au démarrage du système**   
                                
Taper la commande suivante :  
                
                
`blkid`   
                
 ![](https://github.com/infokrim/Checkpoint1/blob/main/exercice1/Partie%202/image12.PNG)     
                 
                
L’exécution de **"blkid"** sans aucun argument répertorie tous les appareils disponibles avec leur identifiant universellement unique (UUID), le type du système de fichiers et l’étiquette si définie.   
                
**L'UUID** de "sdb1" et "sdb2" est nécessaire pour modifier le fichier **"/etc/fstab"** qui contient les commandes de démarrage.   

Le fichier /etc/fstab contient les commandes de démarrage il faut donc le modifier avec la commande :   
                

`nano /etc/fstab`   
                
**la fenêtre suivante s'affiche :**  
                
![](https://github.com/infokrim/Checkpoint1/blob/main/exercice1/Partie%202/image13.PNG)    
                
                
Voici les nouvelles modifications du fichier "/etc/fstab" :
                
![](https://github.com/infokrim/Checkpoint1/blob/main/exercice1/Partie%202/image17.PNG)
                
Touches "Control O" pour enregistrer et "Control X" pour sortir du programme nano.    
                
Liste de commandes pour respectivement recharger la configuration de fstab et activer le swap :   
                
 ```
mount -a  
swapon -a   
 ```   
                
![](https://github.com/infokrim/Checkpoint1/blob/main/exercice1/Partie%202/image16.PNG)  
                
                
Ensuite `reboot`pour redémarrer.
                
                
                
                
                
                
                
                
                
                
                
