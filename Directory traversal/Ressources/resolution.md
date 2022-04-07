Résolution:

La faille Directory traversal consiste à modifier le chemin de l'arborescence dans l'URL afin d’accéder à des répertoires du site non autorisés.

Ici le router fonctione avec des querry du type "?page="nom_de_la_page""
Il suffit d'aller à la racine du syteme et de chercher le dossier contenant les mots de passes sous linux.

http://192.168.56.101/index.php?page=../../../../../../../etc/passwd

Il est possible d'utiliser la commande chroot qui permet de changer un dossier child en fake root. Il n'est plus possible de remonter à sa vraie racine en utilisant "../"
