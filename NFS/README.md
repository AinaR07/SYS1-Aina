# NFS
# 1- Qu il faut savoir
Le NFS, pour Network File System, est un protocole permettant à un ordinateur d'accéder à des fichiers extérieurs via un réseau. Développé dans les années 80, le NFS s'est ensuite imposé comme la norme en matière de serveur de fichiers.

# 2- Installation:
- Sur le serveur Debian, mettez à jour le cache des paquets :
```
$ sudo apt-get update
```
- Puis, installer le paquet "nfs-kernel-server" :
```
$ sudo apt-get install nfs-kernel-server
```
- Configurer le serveur NFS pour qu'il démarre automatiquement avec le système :
```
$ sudo systemctl enable nfs-server.service
```
Le paquet est installé.

# 3-  Déclarer un partage NFS /etc/exports:
-Commençons par créer le partage :
```
$ mkdir /srv/partagenfs
```
-Puis, on applique les droits sur le partage :
```
$ chown nobody:nogroup /srv/partagenfs/
chmod 755 /srv/partagenfs/
```
- Pour déclarer les partages NFS, il faut s'appuyer sur le fichier``` "/etc/exports" ```. 
C'est dans ce fichier que nous allons déclarer notre fichier ``` "/srv/partagenfs" ```. Editer le fichier :

$ sudo nano /etc/exports
- Dans ce fichier, voici la ligne à ajouter pour déclarer notre partage :
```
$ /srv/partagenfs 192.168.100.0/24(rw,sync,anonuid=65534,anongid=65534,no_subtree_check)
```
- Pour que la configuration soit prise en compte :
```
$ exportfs -a
```
- Pour stopper et fermer les partages NFS, il faut exécuter :
```
$ exportfs -ua
```
- Afficher la liste des partages NFS sur l'hôte précisé, c'est à dire notre machine Debian :
```
$ showmount -e 192.168.100.121
```


<a href='https://github.com/AinaR07/SYS1-Aina'>RETOUR</a>
