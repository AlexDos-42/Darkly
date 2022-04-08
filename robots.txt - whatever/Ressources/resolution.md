Résolution:

J'ai utilisé l'outil nmap qui m'a permis de découvrir le fichier robot.txt.
Robot.txt est un fichier qui indique aux robots d'exploration d'un moteur de recherche les URL auxquelles il peut accéder sur votre site.

User-agent: *

Disallow: /whatever

Disallow: /.hidden

Ici il interdit les robots d'aller aux URL /whatever et /.hidden. Mais il n'interdit pas aux users d'y aller.

Celle qui nous interesse est /whatever, qui contient un fichier htpasswd contenant :

root:8621ffdbc5698829397d97767ac13db3

MD5 est un algorithme qui hash les strings. Théoriquement on ne peut pas retrouver la string à partir de la valeur hashée. Mais pour les mots courants il existe une bibliothèque de correspondances qui permet passer de l'un a l'autre.
Si on rentre 8621ffdbc5698829397d97767ac13db3 dans un reverse dictionary, on obtient le mot dragon.

Ensuite si on va a l'address /admin et qu'on rentre l'iddentifiants root et son mot de passe dragon on obtient un nouveau flag.

Il y a beaucoup d'erreurs ici. Robot.txt n'interdit pas l'accès aux users, on ne devrait pas trouver le mot de passe côté front, le mot de passe est trop simple et le hashage pas assez fort (voir résolution cookie).
