# Installation et configuration d'un environnement de test virtuel
****************
```
Prérequis :

Oracle VM Virtualbox installé sur la machine hôte

OS utilisés :

Serveur : Windows Server 2012 R2

Client Windows : Windows 7 Professionnel SP1

Client Linux : Ubuntu 20.04
```
```
Logins : 

Administrateur
Client-PC/Client
satellite               Admin25
jean@test.local 
pierre@test.local

Domaine : test.local
```
# Installation via l'import du fichier .ova

1 . Téléchargez le fichier .ova via le lien https://www.dropbox.com/s/az76yxzenp6epc1/Homelab%20virtuel.ova?dl=0

2 . Dans Oracle VM Virtualbox, cliquez sur **Fichier** puis **Importer un appareil virtuel**, choisissez le fichier précedemment téléchargé, cliquez sur **Suivant**, et suivez l'assistant d'importation

&nbsp;
&nbsp;
&nbsp;
&nbsp;

## Note : Créer une VM sur Oracle VM Virtualbox

1 . Dans la fenêtre d'Oracle VM, cliquez sur **Nouvelle**

2 . Nommez votre machine et choisissez l'OS adapté  

3 . Choisissez la mémoire et la taille du disque dur à allouer (2048/32Go suffisent de manière générale)  

4 . Sélectionnez votre machine créée et cliquez sur **Configuration**

5 . Dans la nouvelle fenêtre, sélectionnez l'option **Stockage et l'unité de Stockage Vide (Icône de CD-ROM)**

6 . **Cliquez sur l'icône de CD sur le côté de Lecteur optique** et sélectionnez l'option **Choose a disk file**

7 . Choisissez l'image disque préalablement téléchargée de l'OS souhaité  


Une fois l'installation de l'OS terminée, pensez à retirer l'ISO de la VM en sélectionnant l'option **Retirer le disque du lecteur virtuel**


Image disques disponibles sur  : https://lecrabeinfo.net/telecharger/cat/systemes-dexploitation

*******
<br>
<br>

# Installation et configuration du Serveur Windows 2012 R2
&nbsp;

## **Installation de l'OS**

1 . Démarrez la machine virtuelle préalablement créée 

2 . Choisissez la langue d'installation et cliquez sur **Installer Maintenant**  

3 . Rentrez la clé produit XC9B7-NBPP2-83J2H-RHMBY-92BT4 et cliquez sur **Suivant**  

4 . Choisissez **l'installation avec une interface graphique**  

5 . Choisissez **l'installation personnalisée** et partitionnez le disque si besoin  

6 . Une fois l'OS installé, choisissez un mot de passe pour l'Administrateur  

7 . Connectez vous à la machine 
&nbsp;
&nbsp;
## **Configuration réseau**

1 . Dans le menu Démarrer rechercher l'option **Centre Réseau et partage**

2 . Sélectionnez **modifier les paramètres de la carte** et effectuez un double clic sur la carte réseau

3 . Cliquez sur **Propriétés** puis sur **Protocole Internet Version 4**

4 . **Attribuez une adresse IP** à votre machine (exemple : 192.168.1.1)

5 . Dans l'onglet **Machine de la fenêtre Virtualbox, cliquez sur **Configuration**

6 . Cliquez sur **Réseau** et choisissez l'option dans le menu déroulant **Réseau interne**
&nbsp;
&nbsp;
<div style="page-break-after: always"></div> 

## **Installation et configuration du serveur d'impression**
1 . Dans le gestionnaire de serveur, Cliquez sur l'option **Tous les serveurs**, effectuez un clic droit sur le serveur et sélectionnez **Ajouter des rôles et des fonctionnalités**

2 . Cliquez sur **Suivant**

3 . Choisissez l’option **Installation basée sur un rôle un ou fonctionnalité** et cliquez sur **Suivant**

4 . Sélectionnez le serveur et cliquez sur **Suivant**

5 . Cocher la case **Service d'impression et de numérisation de documents**

6 . Cliquez sur **Ajouter des fonctionnalités** puis sur **Suivant**

7 . Cliquez sur **Suivant** pour passer la liste des fonctionnalités

8 . Cliquez sur **Suivant** pour passer le résumé des Services d'impression

9 . Sélectionnez le service **Serveur d'impression** et cliquez sur **Suivant**

10 . Cliquez sur **Installer** et fermer l'assistant une fois l'installation terminée
&nbsp;
&nbsp;
## **Ajout des pilotes**

1 . Dans la console **Gestion de l'impression** disponible depuis le menu Démarrer, faites un clic droit sur **Pilotes** dans le menu déroulant à gauche et cliquez sur **Ajouter un pilote**

2 . Cliquez sur **Suivant** lors de l'ouverture de l'assistant

3 . Choisir le type de processeur adapté aux ordinateurs soit **x64** dans notre cas.

4 . Choisissez un pilote dans la liste ou bien ajoutez le manuellement via l'option Disque Fourni

5 . Une fois le pilote installé cliquez sur **Terminer**
&nbsp;
&nbsp;
## **Installation et ajout d'une imprimante**

1 . Dans la console **Gestion de l'impression** disponible depuis le menu Démarrer, faites un clic droit sur **Imprimantes** dans le menu déroulant à gauche et cliquez sur **Ajouter une imprimante**

2 . Choisissez **Rechercher les imprimantes du réseau** et cliquez sur la votre à la fin de la recherche

3 . Une fois l'imprimante installée, cliquez sur **Terminer**, l'imprimante sera disponible dans le noeud Imprimantes du gestionnaire
<div style="page-break-after: always"></div> 

## **Installation du service DHCP**

1 . Dans le **gestionnaire de serveur**, cliquez sur l'option **Tous les serveurs**, effectuez un clic droit sur le serveur et sélectionnez **Ajouter des rôles et des fonctionnalités**

2 . Cliquez sur **Suivant** lors de l'ouverture de l'assistant

3 . Choisissez l’option **Installation basée sur un rôle un ou fonctionnalité** et cliquez sur **Suivant**

4 . Choisissez le serveur et cliquez sur **Suivant**

5 . Cocher la case **Serveur DHCP**

6 . Cliquez sur **Ajouter des fonctionnalités** puis sur **Suivant**

7 . Cliquez sur **Suivant** pour passer la liste des fonctionnalités

8 . Cliquez sur **Suivant** pour passer le résumé du rôle de Serveur DHCP

9 . Cliquez sur **Installer** et fermez l'assistant une fois l'installation terminée
<div style="page-break-after: always"></div> 

## **Configuration du service DHCP**

1 . Cliquez sur **l'alerte** présente dans le gestionnaire de serveur et cliquez sur **Terminer la configuration DHCP**

2 . Cliquez sur **Suivant**

3 . Validez les informations d'identification

4 . Quittez l'assistant en cliquant sur **Fermer**

5 . Sur le gestionnaire, cliquez sur **l'onglet DHCP** et descendez dans la partie **Services**, faites-y un clic droit sur le service en cours et cliquez sur **Redémarrer les services**

6 . Dans le **gestionnaire DHCP** (accessible depuis le menu Démarrer), dérouler l'arborescence à gauche et faites un clic droit sur **IPv4** et cliquez sur **Nouvelle étendue**

7 . Passer la fenêtre de l'assistant en cliquant sur **Suivant**

8 . Donnez un nom à l'étendue et cliquez sur **Suivant**

9 . **Entrez une plage d'adresse disponible** (exemple : 192.168.1.2 à 192.168.1.100)

10 . Passez les exclusions et les retards en cliquant sur **Suivant**

11 . **Configurez la durée du bail**, qui correspond à la durée auquel le futur poste aura l'adresse IP et cliquez sur **Suivant**

12 . Choisissez **Oui, je veux configurer ces options maintenant** et cliquez sur **Suivant**

13 .**Indiquez l'adresse IP du routeur** soit 192.168.1.1 et cliquez sur **Ajouter**

14 . Cliquez sur **Suivant**

15 . Validez les informations du nom de domaine parent et cliquez sur **Suivant**

16 . Passez l'option des serveurs WINS en cliquant sur **Suivant**

17 . Sélectionnez **Oui, je veux activer cette étendue maintenant** et cliquez sur **Suivant**

18 . Fermez l'assistant en cliquant sur **Terminer**

(Note : Sur les ordinateurs clients, dans le paramétrage d'adresse IP choisissez l'option Obtenir une adresse automatiquement pour utiliser le service DHCP)

<div style="page-break-after: always"></div> 

## **Installation de l'Active Directory**


1 . Dans le **gestionnaire de serveur**, Cliquez sur l'option **Tous les serveurs**, effectuez un clic droit sur le serveur et sélectionnez **Ajouter des rôles et des fonctionnalités**

2 . Dans la fenêtre d'assistance, cliquez sur **Suivant**, sélectionner l'option **Installation basée sur un rôle ou une fonctionnalité** et cliquez sur **Suivant**

3 . Sélectionner le serveur de destination et cliquez sur **Suivant**

4 . Cochez le rôle **Services AD DS** et cliquez sur **Ajouter des fonctionnalités** dans la nouvelle fenêtre, cliquez sur **Suivant**

5 . Cliquez sur **Suivant** pour les deux prochaines sections et terminez la configuration en cliquant sur **Installer**

6 . Une fois l’installation terminée , sélectionnez **l’icône d'alerte** et cliquez sur **Promouvoir ce serveur en contrôleur de domaine**

7 . Dans la nouvelle fenêtre , Cochez **Ajouter une nouvelle forêt** et mettre en nom de domaine racine : test.local, cliquez sur **Suivant**, ajoutez un mot de passe de mode de restauration des services d'annuaire, cliquez sur **Suivant** deux fois, mettez comme nom de NetBIOS test en majuscule, cliquez sur **Suivant** deux fois et finissez la configuration en cliquant sur **Installer**

8 . Dans le gestionnaire de serveur sélectionnez **l'Onglet AD DS**, effectuez un clic droit sur le serveur, choisissez l'option **Utilisateurs et ordinateurs Active Directory**, effectuez un clic droit sur le domaine en .local, cliquez sur **Nouveau puis Utilisateur**, choisissez les logins, cliquez sur **Suivant** et décochez **l'utilisateur doit changer le nouveau mot de passe...** et cocher la case **le mot de passe
n’expire jamais**
<div style="page-break-after: always"></div> 

# Installation et configuration du Client Windows 7

## **Installation de l'OS**  

1 . Démarrez la machine virtuelle préalablement créée

2 . Choisissez la langue d'installation , cliquez sur **Suivant** et sur **Installer Maintenant**  

3 . Cocher les termes du contrat de licence et cliquez sur **Suivant**

4 . Choisissez **l'installation personnalisée** et partitionnez le disque si besoin , cliquez sur **Suivant**

5 . Choisissez un nom d'utilisateur et un mot de passe et cliquez sur **Suivant**

6 . Cliquez sur **Ignorer pour la clé de produit**

7 . Choisissez **Utiliser les paramètres recommandés** et cliquez sur **Suivant**

8 . Sélectionnez **Réseau public**
&nbsp;
&nbsp;
## **Configuration réseau**

1 . Dans le menu Démarrer rechercher l'option **Centre Réseau et partage**

2 . Sélectionnez **modifier les paramètres de la carte** et effectuez un double clic sur la carte réseau

3 . Cliquez sur **Propriétés** puis sur **Protocole Internet Version 4**

4 . **Attribuez une adresse IP** à votre machine et **entrer l'adresse DNS** soit l'IP du serveur Windows 2012 R2

5 . Dans l'onglet **Machine** de la fenêtre Virtualbox, cliquez sur **Configuration**

6 . Cliquez sur **Réseau** et Choisissez l'option dans le menu déroulant **Réseau interne** 

7 . Pour relier au domaine la machine cliente, dans l’explorateur Windows, effectuez un clic droit sur **Ordinateur**, Choisissez **Propriétés** -> **modifier les paramètres** -> **modifier et dans domaine** mettre le nom de domaine préalablement choisi (Installation et configuration du Serveur Windows 2012 R2 / Installation de l'Active Directory - étape 7), rentrez les logins de l'administrateur Windows Serveur et **redémarrez la machine cliente** une fois la connexion au domaine établie.

8 . Connectez vous avec le nouvel utilisateur AD préalablement crée

<div style="page-break-after: always"></div> 

# Installation et configuration du Client Linux  
&nbsp;

## **Installation de l'OS**

1 . Démarrez la machine virtuelle préalablement créée

2 . Cliquez sur **Installer Ubuntu**

3 . Choisissez la langue d'installation et cliquez sur **Continuer**

4 . Choisissez **Installation normale** et cliquez sur **Continuer**

5 . Choisissez **Effacer le disque et installer Ubuntu** et **cliquez sur Installez maintenant**

6 . Cliquez sur **Continuer** dans la nouvelle fenêtre pour appliquer les changements sur le disque

7 . Choisissez le fuseau horaire adapté et cliquez sur **Continuer**

8 . Choisissez les logins et cliquez sur **Continuer**

9 . Une fois l'installation terminée, redémarrez la machine

<div style="page-break-after: always"></div>  

## **Configuration réseau**

1 . Ouvrez un terminal et lancez les commandes suivantes :  

```
sudo apt -y update
sudo hostnamectl set-hostname client.test.local
nano /etc/hosts et ajouter  client.test.local après localhost
sudo nano /etc/resolv.conf et ajouter nameserver IPSERVEURWINDOWS
sudo apt -y install realmd libnss-sss libpam-sss sssd sssd-tools adcli samba-common-bin oddjob oddjob-mkhomedir packagekit
```
2 . Dans la barre des tâches en haut à droite, cliquez sur l'option **réseau** et sélectionnez **paramètres filaire**

3 . Cliquez sur l'icône **paramètres** dans le menu **Filaire**

4 . Sélectionnez l'onglet **IPV4** et indiquer une adresse IP, le masque de sous-réseau et l'IP du serveur DNS soit l'IP du serveur Windows 2012 R2

5 . Redémarrez la carte réseau pour appliquer les changements 

6 . Dans l'onglet **Machine** de la fenêtre Virtualbox, cliquez sur **Configuration**

7 . Cliquez sur **Réseau** et Choisissez l'option dans le menu déroulant **Réseau interne**

8 . Pour relier au domaine la machine cliente lancez les commandes suivantes :

```
sudo realm discover test.local
sudo realm join -U Administrateur test.local

sudo bash -c "cat > /usr/share/pam-configs/mkhomedir" <<EOF
Name: activate mkhomedir
Default: yes
Priority: 900
Session-Type: Additional
Session:
        required                        pam_mkhomedir.so umask=0022 skel=/etc/skel
EOF
```
```
sudo pam-auth-update
Cocher l'option activate mkhomedir

sudo systemctl restart sssd
id UserAD
sudo realm permit userad@test.local
```

9 . Fermez la session et connectez vous avec un utilisateur de l'AD

<div style="page-break-after: always"></div>  


