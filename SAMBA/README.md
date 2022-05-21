# Le serveur SAMBA

# 1- Qu il faut savoir
Un serveur Linux-Samba permet d'organiser les autorisations de partage de données et autres services en réseau (comme un serveur Windows), mais aussi de prendre en charge le rôle d'Active Directory Domain Controllers.
# 2- Installation
  - la ligne de commande :
```
$sudo apt update
$sudo apt install samba
```
  - vérification de l'installation:
```
$sudo whereis samba
```
  - Alors:
```
samba: /usr/sbin/samba /usr/lib/samba /etc/samba /usr/share/samba /usr/share/man/man7/samba.7.gz /usr/share/man/man8/samba.8.gz
```

# 3 - Configuration
- repertoire partagé:
```
$sudo mkdir /home/herilala/sambashare/
```

  - Le fichier de configuration : **/etc/samba/smb.conf**.

  - Nouveau répertoire sous forme de partage:  "/etc/samba/smb.conf" :

```
$sudo nano /etc/samba/smb.conf
```

Ajout de lignes :
```
[sambashare]
    comment = Samba on Linux
    path = /home/<username>/sambashare
    read only = no
    browsable = yes
```

- redemarrer le serveur
```
$sudo service smbd restart
```
- Mise a jour du pare-feu ufw pour autoriser Samba :
```
$sudo ufw enable   
$sudo ufw allow samba   
$sudo ufw reload   
```


<a href='https://github.com/AinaR07/SYS1-Aina'>RETOUR aux autres serveurs </a>
