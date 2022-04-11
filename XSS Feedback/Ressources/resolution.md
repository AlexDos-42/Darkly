Résolution: 
 
Pour tester si une attaque cross-site scripting (XSS) est possible, j'ai copié le mini-script suivant dans chaque form du site.
<script>alert('Darkly')</script>

Et on trouve un flag quand on sign le guestbook avec un script a la place du Name à l'addresse suivante :
http://192.168.56.101/?page=feedback

Pour se proteger de ce type d'attaque il faut "Escape Dynamic Content". C'est a dire, remplacer des caractères significatifs pour ne plus lire du code mais un simple texte.
Exemple: <	devient &#60
et donc <script> peut s'écrire &#60script&#62
Les frameworks modernes gèrent se probablème automatiquement.

