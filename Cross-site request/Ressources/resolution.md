Résolution:

Dans la page des credits:
http://192.168.56.101/index.php?page=e43ad1fdc54babe674da7c7b8f0127bde61de3fbe01def7d00f151c2fcca6d1c

On peut trouver dans le code html, les informations commentés suivantes:
"You must cumming from : "https://www.nsa.gov/" to go to the next step"
"Let's use this browser : "ft_bornToSec". It will help you a lot."

De la, on va faire une requête avec comme referer https://www.nsa.gov/ et user-agent ft_bornToSec.

Eviter de laisser des informations commentées côté front, et utiliser un système de token pour iddentifier l'utilisateur pour refuser les requêtes non autorisées.
