Résolution:

A l'adresse du survey:
http://192.168.56.101/index.php?page=survey

On peut envoyer une note de 1 à 10 pour chaque sujet. Mais si on modifie le dom, on peut post une valeur superieur à 10.

Il suffirait de faire un check côté back et renvoyer une erreur si la réponse n'est pas un int compris entre 1 et 10.
