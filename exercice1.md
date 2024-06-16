
## **<ins>Exercice 1 - Gestion du stockage</ins>**
________________________________________________________


###  <ins>**1.1 Préparation du disque 2**</ins>**

####        **a. Première étape : création des partitions**  
####            **-Première partition de 6Go**  

                "lsblk" est un programme qui affiche les différents périphériques de la VM (virtual machine).  
                Taper `lsblk`  


                **la fenêtre suivante s'affiche :**  


                 ![](https://example.com/image1b.jpg)


                Le second disque est **sdb**.


                **Commandes pour partitionnement :**

                `Cfdisk /dev/sdb`  


                **"cfdisk"** est un programme de manipulation de tables de partitions.  
                **"/dev/sdb"** est le disque sur lequel il faut créer deux partitions.  
                 
                **la fenêtre suivante s'affiche :**  



                ![](C:\Users\PC\Desktop\Mon bureau\Formation\Checkpoint\exrecice1cor\image2b.jpg)


                Choisir **Dos** pour le type de partition demandé.  
                  
                  
                **la fenêtre suivante s'affiche :**  


                 ![](C:\Users\PC\Desktop\Mon bureau\Formation\Checkpoint\exercice1cor\image3.png)
                 
                 
                Le disque **"sdb"** est affiché comme espace libre (donc non partitionné) et indique une taille de 10 Go.  

                Choisir **"Nouvelle"** (appuyer sur la touche n).

                **la fenêtre suivante s'affiche :**  


                 ![](C:\Users\PC\Desktop\Mon bureau\Formation\Checkpoint\exercice1cor\image4.png)


                Donner la taille de 6Go à la partition désirée (remplacer 10G par 6G) et appuyer sur entrée.


                **la fenêtre suivante s'affiche :**  



                 ![](C:\Users\PC\Desktop\Mon bureau\Formation\Checkpoint\exercice1cor\image5.png)
                 
                 
                 
                Choisir **partition primaire** pour le type demandé


                **la fenêtre suivante s'affiche :**  


                 ![](C:\Users\PC\Desktop\Mon bureau\Formation\Checkpoint\exercice1cor\image6.png)
                 
                 
                 **la fenêtre suivante s'affiche :**  
                 
                 
                  ![](C:\Users\PC\Desktop\Mon bureau\Formation\Checkpoint\exercice1cor\image7.png)
                  
                 
                Le type de la partition apparait en bas au dessus des options, "Linux (83)" pour partition linux (définit par défaut)

                 
                  ![](C:\Users\PC\Desktop\Mon bureau\Formation\Checkpoint\exercice1cor\image7b.png)  
                   
  
  
####            **-Deuxième partition (SWAP)**  
                
                Sur le disque "sdb", il reste un espace libre de 4 Go.
                
                
                ![](C:\Users\PC\Desktop\Mon bureau\Formation\Checkpoint\exercice1cor\image7bb.png)
                
                
                             
                4 Go sera la taille de la deuxième partition "SWAP".
                
                
                ![](C:\Users\PC\Desktop\Mon bureau\Formation\Checkpoint\exercice1cor\image8.png)  
                       
                
                
                Toujours dans le programme cfdisk, choisir l'action "Nouvelle".
                Pour cela avec la flèche du bas(du clavier), se positionner sur "esapce libre"  
                Appuyer sur la touche n (ou se positionner sur "Nouvelle" avec la flèche gauche du clavier, puis appuyer sur la touche "entrée").  
                
                Laisser la taille de partition à **4Go** (4G espace libre restant affiché).  
                
                ![](C:\Users\PC\Desktop\Mon bureau\Formation\Checkpoint\exercice1cor\image9.png)  

                
                Choisir Primaire, pour le type de partition

                ![](C:\Users\PC\Desktop\Mon bureau\Formation\Checkpoint\exercice1cor\image10.png)

                
                **la fenêtre suivante s'affiche :**  
                
                
                ![](C:\Users\PC\Desktop\Mon bureau\Formation\Checkpoint\exercice1cor\image11.png)  
                
                Appuyer sur la touche T (comme type), (ou se positionner sur "Type" en navigant avec les flèches gauche et droite du clavier, puis appuyer sur la touche "entrée").  
                
                
                **la fenêtre suivante s'affiche :**  
                
                
                ![](C:\Users\PC\Desktop\Mon bureau\Formation\Checkpoint\exercice1cor\image12.png)


                Pour choisir le type de partition SWAP, se positionner sur **"82 partition d’échange Linux/Solaris"**  
                
                **la fenêtre suivante s'affiche :**  
                
                
                ![](C:\Users\PC\Desktop\Mon bureau\Formation\Checkpoint\exercice1cor\image13.png)
                
                
                Le disque **"sdb"** est maintenant divisé en deux partitions.  
                **Une partition "sdb1" de type "linux" d'une taille de 6 Go.**
                **Une partition "sdb2" de type "partition d’échange Linux/Solaris" d'une taille de 4 Go.**  
                
                
                **(logo attention)**Il faut écrire les partitions du disque crées pour qu'elles soient crées réellement.  
                
                Séléctionner "Ecrire" puis appuyer sur la touche "Entrée"(ou appuyer sur la touche E du clavier) pour enregistrer les partitions créées. 

                
                ![](C:\Users\PC\Desktop\Mon bureau\Formation\Checkpoint\exercice1cor\image13b.png)  
                                
                
                **la fenêtre suivante s'affiche :** 
                
                
                ![](C:\Users\PC\Desktop\Mon bureau\Formation\Checkpoint\exercice1cor\image14.png)  


                Taper le mot "oui" puis appuyer sur la touche "Entrée" pour effectuer l'écriture des partitions sur le disque.  
                
                
                ![](C:\Users\PC\Desktop\Mon bureau\Formation\Checkpoint\exercice1cor\image14bb.png)  
                
                
                ![](C:\Users\PC\Desktop\Mon bureau\Formation\Checkpoint\exercice1cor\image14b2.png)  
                
                
                "La table de partitionsa été altérée." (en bleu sur l'image du dessus indique que l'écriture des partitions est effective.   
                
                
                Quitter le programme en appuyant sur la touche "Q" du clavier 
                
                
                **la fenêtre suivante s'affiche :**  
                
                
                La commande "clear" permet de nettoyer l'écran pour la deuxième de l'exercice.   
                
                
                
####        **b. Deuxième étape : Formatage des partitions crées**  


                **- disque sdb1**
                
                Taper la commande "lsblk" pour afficher l'arborescence des disques
                
                `lsblk`
                
                
                **la fenêtre suivante s'affiche :**  
                
                ![](C:\Users\PC\Desktop\Mon bureau\Formation\Checkpoint\exrecice1cor\Partie_2\image1.png)  
                
                Les deux partitions crées avant (**sdb1** et sdb2**) doivent être maintenant formatées.
                
                **Formatage de la partition sdb1**  
                
                Taper la ligne de commande suivante :   
                
                **`mkfs.ext4 -L DATA /dev/sdb1`**  
                
                **`mkfs.ext4`** formate la partition en ext4.   
                
                **`-L DATA`** donne le nom DATA à la partition formatée.  
                
                **`/dev/sdb1`** correspond à la partition à formater.  
                
                ![](C:\Users\PC\Desktop\Mon bureau\Formation\Checkpoint\exrecice1cor\Partie_2\image2.png) 
                
                Les mots "done" sur les différentes lignes affichées (étapes du formatage) indiquent que l'opération s'est bien passée.    
                Pour avoir la preuve, la commande "lsblk" suivie de l'option "-f" permet d'afficher plus de détails sur less périphériques.   
                
                
                Taper la commande suivante : 
                
                `lsblk -f`  
                
                
                ![](C:\Users\PC\Desktop\Mon bureau\Formation\Checkpoint\exrecice1cor\Partie_2\image3.png)  
                
                             
                               
                La colonne "FSTYPE" indique le type **"ext4"** et la colonne **"LABEL"** indique le nom **"DATA"**  pour **"sdb1"**.  
                
                
                **Formatage de la partition sdb2**   
                
                
                Taper la commande suivante : 
                
                
                `mkswap /dev/sdb2`
                
                
                Cette commande crée une zone d'échange Linux sur le périphérique "/dev/sdb2".  
                
                Pour activer la partition "sdb2" utiliser la commande "swapon"   
                

                `swapon /dev/sdb2`  
                
                
                "swapon" est utilisé pour indiquer les périphériques sur lesquels la pagination et l'échange auront lieu.
                " /dev/sdb2" indique la partition a activer en swap.   
                
                ![](C:\Users\PC\Desktop\Mon bureau\Formation\Checkpoint\exrecice1cor\Partie_2\image4.png) 
                   
                
                Quand on tape la commande "lsblk", on remarque qu'une partition "SWAP" est déjà crée sur la partition "sda5".  
                
                
                 ![](C:\Users\PC\Desktop\Mon bureau\Formation\Checkpoint\exrecice1cor\Partie_2\image5.png)
                 
                 
                Il est possible d'avoir plusieurs partitions SWAP sur une machine, mais une seule partition SWAP suffit.  
                
                Pour désactiver la partition "SWAP" existante sur  sda 5, taper la commande suivante :       
                
                `swapoff /dev/sda5`  
                
                 ![](C:\Users\PC\Desktop\Mon bureau\Formation\Checkpoint\exrecice1cor\Partie_2\image6.png)

                puis taper  
                
                
                `lsblk `  
                
                
                 ![](C:\Users\PC\Desktop\Mon bureau\Formation\Checkpoint\exrecice1cor\Partie_2\image7.png)   
                 
                 "sdb2" est maintenant la seule partition d'échange "SWAP".  
                 
                 
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
                
                
                `cd /` se positionner dans le dossier racine (root)  
                `ls` liste les dossiers et fichiers du répertoire courant (ici répertoire root).  
                `mkdir /mnt/data` créer le dossier "data" dans le dossier "/mnt"
                `cd mnt` se positionner dans le dossier mnt (/mnt est le répertoire utilisé pour monter temporairement un système de fichiers.  
                `ls` liste les dossiers et fichiers du répertoire courant.  
                `ls data` vérification contenu dossier data (normalement vide puisque nouvellement crée).  

                
                ![](C:\Users\PC\Desktop\Mon bureau\Formation\Checkpoint\exrecice1cor\Partie_2\image10.png)  
                
                
                
                **Montage du dossier data**
                
                Taper la commande :   
                
                **`mount -t ext4 /dev/sdb1 /mnt/data`**   
               
                
                
                `mount` : La commande mount est utilisée pour monter un système de fichiers (comme une partition) sur un répertoire spécifié.   
                
                
                `-t ext4 ` : L’option "-t" spécifie le type de système de fichiers. Dans ce cas, nous utilisons ext4.   
                
                
                `/dev/sdb1` : C’est le périphérique (ou la partition) que nous voulons monter. /dev/sdb1 fait référence à la première partition du disque "sdb".  
                
                
                `/mnt/data` : C’est le répertoire de montage. Une fois la partition montée, son contenu sera accessible via ce répertoire.  
                
                
                puis taper  
                
                
                `lsblk `  
                
                
                ![](C:\Users\PC\Desktop\Mon bureau\Formation\Checkpoint\exrecice1cor\Partie_2\image11.png) 
                
                
                La partition **"sdb1"** est bien montée dans le répertoire de montage **"/mnt/data"**.   
                
                
                
                **Montage automatique de la partition DATA au démarrage du système**   
                                
                Taper la commande suivante :  
                
                
                `blkid`   
                
                ![](C:\Users\PC\Desktop\Mon bureau\Formation\Checkpoint\exrecice1cor\Partie_2\image12.png)
                
                
                
                L’exécution de **"blkid"** sans aucun argument répertorie tous les appareils disponibles avec leur identifiant universellement unique (UUID), le type du système de fichiers et l’étiquette si définie.   
                
                L'UUID de "sdb1" et "sdb2" est nécessaire pour modifier le fichier **"/etc/fstab"** qui contient les commandes de démarrage.   

                Le fichier /etc/fstab contient les commandes de démarrage il faut donc le modifier avec la commande :   
                

                `nano /etc/fstab`   
                
                **la fenêtre suivante s'affiche :**  
                
                ![](C:\Users\PC\Desktop\Mon bureau\Formation\Checkpoint\exrecice1cor\Partie_2\image13.png)    
                
                
                Voici les nouvelles modifications du fichier "/etc/fstab" :
                
                ![](C:\Users\PC\Desktop\Mon bureau\Formation\Checkpoint\exrecice1cor\Partie_2\image14.png)  
                
                Touches "Control O" pour enregistrer et "Control X" pour sortir du programme nano.    
                
                Liste de commandes pour respectivement recharger la configuration de fstab et activer le swap :   
                
                ```
                mount -a  
                swapon -a   
                ```   
                
                ![](C:\Users\PC\Desktop\Mon bureau\Formation\Checkpoint\exrecice1cor\Partie_2\image16.png)
                
                
                Ensuite `reboot`
                
                
                
                
                
                
                
                
                
                
                