# Le serveur NGINX
# 1 - Qu il faut savoir
Nginx est l'un des serveurs web les plus populaires au monde et se charge de l'hébergement de certains des sites les plus importants et les plus fréquentés sur Internet. C'est une option légère qui peut être utilisée comme serveur web ou proxy inverse.

# 2 -Installation et configuration
- Actualiser les différents éléments du paquet NGINX de manière à posséder les versions les plus récentes:
```
$ sudo apt-get update
$ sudo apt-get install nginx
```
- Vérifier si le logiciel fonctionne en bonne et due forme, charger la "landingpage de NGINX"

``` "WELCOME TO NGINX" ``` s'affiche ---> c'est instlallé
-  Pour la configuration consulter le dossier: 
```
/etc/nginx 
```
et dans le fichier de configuration:
```
nginx.conf. 
```
- A chaque modifications, il est nécessaire de redémarrer le serveur, commandes:
```
$ sudo service nginx reload
```
```
$ sudo service nginx restart
```
 Les paramètres stop et start, On peut interrompre et reprendre le service en cours.
- La syntaxe du fichier de configuration présente les caractéristiques suivantes :
○ Réglages : tous les réglages commencent par le nom variable respectif. Un espace vide délimite deux arguments et la ligne se termine toujours par un point-virgule.
```
$ worker_connections 768;
```
○ Paramètres avancés : certains paramètres tels que les events-variable comportent des arguments qui leurs sont propres. Ces sous-directives sont entourées par des accolades ({}).
```
$ events {

  worker_connections 768;

  multi_accept on;

}
```
○ Signe dièse (#): Il s’agit de directives (instructions) désactivées à l’aide du caractère dièse. En enlevant ce signe, On réactive le réglage correspondant.
```
 --> # multi_accept on;
 ```
○ Tabulations et espaces vides : NGINX interprète les espaces libres multiples et les tabulations comme un seul espace vide. Lors de la configuration de NGINX,
il convient de faire attention à la propreté et lisibilité de la structure du ficher de configuration.

<a href='https://github.com/AinaR07/SYS1-Aina'>RETOUR</a>
