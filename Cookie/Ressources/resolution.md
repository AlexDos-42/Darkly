Résolution:

J'ai utilisé l'add-on EditThisCookie qui permet de voir et d'éditer les cookies.
On trouve le cookie I_Am_The_Admin qui a la valeur de 68934a3e9455fa72420237eb05902327.

MD5 est un algorithme qui hash les strings. Théoriquement on ne peut pas retrouver la string à partir de la valeur hashée.
Mais pour les mots courants il existe une bibliothèque de correspondances qui permet passer de l'un a l'autre.
Si on rentre 68934a3e9455fa72420237eb05902327 dans un reverse dictionary, on obtient le mot false.
Ensuite, il suffit de hasher le mot true b326b5062b2f0e69046810717534cb09 et remplacer false avec l'add-on.
On actualise et voilà.

Il est possible d'utiliser des algorithmes de hashage plus "puissant" comme SHA-2, combiner des algorithmes ou utiliser un salt qui est une string aléatoire à combiner avec le mot non-hashé, pour avoir un résultat qui ne soit dans aucune liste.
