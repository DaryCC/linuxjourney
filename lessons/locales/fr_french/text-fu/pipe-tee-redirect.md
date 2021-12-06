## pipe et tee

## Contenu de la leçon

Passons à la plomberie maintenant, pas vraiment mais un peu. Essayons une commande : 

<pre>$ ls -la /etc</pre>

Vous devriez voir une très longue liste d'éléments, c'est un peu difficile à lire en fait. Au lieu de rediriger cette sortie vers un fichier, ne serait-ce pas bien si nous pouvions simplement voir la sortie dans une autre commande comme less ? Et bien nous le pouvons !

<pre>$ ls -la /etc | less </pre>

L'opérateur pipe | , représenté par une barre verticale, nous permet de récupérer le stdout d'une commande et d'en faire le stdin d'un autre processus. Dans ce cas, nous avons pris le stdout de ls -la /etc et l'avons ensuite <i>pipé</i> vers la commande less. La commande pipe est extrêmement utile et nous continuerons à l'utiliser pour l'éternité. 

Et si je voulais écrire la sortie de ma commande dans deux flux différents ? C'est possible avec la commande tee : 

<pre>$ ls | tee peanuts.txt</pre>

Vous devriez voir la sortie de ls sur votre écran et si vous ouvrez le fichier peanuts.txt vous devriez voir la même information !

## Exercice

Essayez les commandes suivantes : 
<pre>$ ls | tee peanuts.txt banan.txt</pre>

## Question d'interrogation

Quelle clé représente l'opérateur pipe ?

## Réponse au quiz

|