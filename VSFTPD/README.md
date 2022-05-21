#Le serveur VSFTPD
# 1 -Qu il faut savoir
  - VsFTPd est un serveur FTP conçu avec la problématique d'une sécurité maximale. Contrairement aux autres serveurs FTP (ProFTPd, PureFTPd, etc.), aucune faille majeure de sécurité n'a jamais été décelée dans VsFTPd.

Néanmoins deux failles permettant un DoS avaient été détectées, la première était due à une faille d'un vieux noyau linux (avant 2.6.35), et la deuxième a été très vite corrigée.

Ce serveur est utilisé à grande échelle, notamment par des entreprises telles que Red Hat.

# 2 -Installation et configuration
  - La configuration par défaut de VsFTPd est très restrictive :

Seul le compte anonyme est autorisé à se connecter au serveur
En lecture seule
Les utilisateurs ne peuvent pas accéder à leurs répertoires

  - Dans le terminal, saisir la commande suivante pour installer Vsftpd :
```
$sudo apt update
$sudo apt install vsftpd -y
$sudo apt install vsftpd -v
```

  - Verification:

```
$sudo systemctl status vsftpd
```
  - Pour une partage de fichier, il est nécessaire d'utiliser un application comme FileZila, qui est une application FTP multiplateforme gratuite et open source, composée de FileZilla Client et FileZilla Server.

  - On peut télécharger gratuitement FileZila dans ce lien: 
 <https://filezilla-project.org/>
  Ajout d'un nouveau utilisateur
Afin d'établir un transfert de fichier pour un mutli-user, il est important d'ajouter des utilisateur pour interagir avec le serveur.

Voici les étapes à suivre:

- Ajouter un utilisateur

```
$sudo adduser ftpuser
```

- creation de nouveau utilisateur (dossier)
```
$sudo mkdir /home/ftpuser/ftp
$sudo mkdir /home/ftpuser/ftp/fichier
```

- Changer la permission et la propriétaire du dossier

```
$sudo chown nobody:nogroup /home/ftpuser/ftp 
$sudo chmod a-w /home/ftpuser/ftp
$sudo chown ftpuser:ftpuser /home/ftpuser/ftp/fichier
```

##  Configuration du serveur VSFTPD
- creation backup pour le ficher vsftpd.conf

```
$sudo cp /etc/vsftpd.conf /etc/vsftpd.conf.bak
```

  - Modification du ficher vsftpd.conf

```
$sudo nano /etc/vsftpd.conf
```

  - Vérification du serveur vsftpd

```
$sudo systemctl restart vsftpd
$sudo systemctl status vsftpd
```

###  Test du serveur VSFTPD

```
$sudo cd /home/ftpuser/ftp/fichier
$/home/ftpuser/ftp/fichier# ls -al
```

<a href='https://github.com/AinaR07/SYS1-Aina'>RETOUR aux autres serveurs</a>
