# Serveur HTTP Apache 2

# 1- Qu il faut savoir
 - C'est un logiciel de serveur web gratuit et open-source qui alimente environ 46% des sites web à travers le monde.
 Apache renvoie une réponse avec tous les fichiers demandés (texte, images, etc.). Le serveur et le client communiquent via le 
 protocole http et Apache est responsable de la communication fluide et sécurisée entre les deux machines.

 # 2- Procedure d' installation
 - Télécharger apache sur internet
 - Mettre à jour l'index local de package:
   $ sudo apt update
``` 
 $ sudo apt update
 ```
 - Installer le package: 
 ```  
   $ sudo apt install apache2
 # 4- Commandes utiles
```
# 3- Configuration
Configuration http:Le module mod_ssl est disponible dans le paquet apache2-common. 
- Commande pour activer le module mod_ssl :
```
$ sudo a2enmod ssl
```
- Pour configurer Apache2 pour HTTPS:
```
$ sudo a2ensite default-ssl
```
- Avec Apache2 maintenant configuré pour HTTPS, redémarrer le service pour activer les nouveaux paramètres :
``` 
$ sudo systemctl restart apache2.service
```
# 4- Commandes utiles
- Pour arrêter apache2 :  
```
$ sudo systemctl stop apache2
```
- Pour lancer apache2 :  
``` 
$ sudo systemctl start apache2
```
- Pour relancer apache2 :
```  
$ sudo systemctl restart apache2
```
- Pour recharger la configuration d'apache2 :  
```
$ sudo systemctl reload apache2
```
- Pour voir la version d'Apache utilisée :  
```
$ sudo apache2ctl -v
```
- Pour tester l'ensemble de la configuration d'Apache :   
```
$ sudo apache2ctl -t
```
- Pour tester la configuration des hôtes virtuels :  
```
$ sudo apache2ctl -t -D DUMP_VHOSTS
```
- Pour voir les modules d'Apache chargés :
```
$ sudo apache2ctl -M 
```


<a href='https://github.com/AinaR07/SYS1-Aina'>RETOUR aux autres serveurs</a>
