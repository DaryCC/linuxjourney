# stdin (Entrée standard)

## Contenu de la leçon

Dans la leçon précédente, nous avons appris qu'il existe différents flux stdout que nous pouvons utiliser, comme fichier ou à l'écran. Mais il existe également différents flux d'entrée standard (stdin) que nous pouvons utiliser. Nous savons que le flux stdin provient de périphériques tels que le clavier, mais nous pouvons également utiliser des fichiers, la sortie depuis d'autres processus ainsi que depuis le terminal, voyons un exemple. 

Utilisons le fichier peanuts.txt de la leçon précédente pour cet exemple, rappelez-vous qu'il contenait le texte Hello World. 

<pre>$ cat <b>&lt;</b> peanuts.txt <b>&gt;</b> banana.txt </pre>

Tout comme nous avions <b>&gt;</b> pour la redirection de stdout, nous pouvons utiliser <b>&lt;</b> pour la redirection de stdin. 

Normalement dans la commande cat, vous lui envoyez un fichier et ce fichier devient le stdin , (notre entée) . De ce fait la sortie de cat peanuts.txt, qui serait Hello World, est redirigée vers un autre fichier appelé banana.txt.

## Exercice

Essayez quelques commandes :
<pre>
$ echo <b>&lt;</b> peanuts.txt <b>&gt;</b> banana.txt
$ ls <b>&lt;</b> peanuts.txt <b>&gt;</b> banana.txt
$ pwd <b>&lt;</b> peanuts.txt <b>&gt;</b> banana.txt
</pre>

## Questionnaire

Quel redirecteur utilisez-vous pour rediriger stdin ?

## Réponse au quiz
