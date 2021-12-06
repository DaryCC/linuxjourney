
# stderr (Erreur standard)

## Contenu de la leçon

Essayons maintenant quelque chose d'un peu différent, essayons de lister le contenu d'un répertoire qui n'existe pas sur votre système et redirigeons à nouveau la sortie vers le fichier peanuts.txt.

<pre>$ ls /fake/directory > peanuts.txt </pre>

Ce que vous devriez voir est : 

<pre>ls : cannot access /fake/directory : No such file or directory</pre>

Maintenant, vous vous dites probablement que ce message n'aurait-il pas dû être envoyé au fichier ? Il y a en fait un autre flux d'E/S en jeu ici, appelé erreur standard (stderr). Par défaut, stderr envoie sa sortie à l'écran également, c'est un flux complètement différent de stdout. Vous devrez donc rediriger sa sortie d'une manière différente. 

Malheureusement, le redirecteur n'est pas aussi agréable que l'utilisation de <b>&lt;</b> ou <b>&gt;</b> mais c'est assez proche. Nous allons devoir utiliser des descripteurs de fichiers. Un descripteur de fichier est un nombre non négatif qui est utilisé pour accéder à un fichier ou à un flux. Nous approfondirons ce sujet plus tard, mais pour l'instant sachez que le descripteur de fichier pour stdin, stdout et stderr est respectivement 0, 1 et 2. 

Donc, maintenant, si nous voulons rediriger notre stderr vers le fichier, nous pouvons faire ceci : 

<pre>$ ls /fake/directory 2> peanuts.txt</pre>

Vous devriez voir seulement les messages stderr dans peanuts.txt. 

Maintenant, que faire si je voulais voir à la fois stderr et stdout dans le fichier peanuts.txt ? Il est possible de faire cela avec les descripteurs de fichiers également : 

<pre>$ ls /fake/répertoire > peanuts.txt 2>&1</pre>

Ceci envoie les résultats de ls /fake/directory vers le fichier peanuts.txt, puis redirige stderr vers stdout via 2>&1. L'ordre des opérations est important ici, 2>&1 envoie stderr vers ce vers quoi stdout pointe. Dans ce cas, stdout pointe vers un fichier, donc 2>&1 envoie également stderr vers un fichier. Ainsi, si vous ouvrez le fichier peanuts.txt, vous devriez voir à la fois stderr et stdout. Dans notre cas, la commande ci-dessus n'envoie que stderr.

Il existe un moyen plus court de rediriger à la fois stdout et stderr vers un fichier :

<pre>$ ls /fake/directory &> peanuts.txt</pre>

Maintenant, que faire si je ne veux pas de ce truc et que je veux me débarrasser complètement des messages stderr ? Eh bien, vous pouvez également rediriger la sortie vers un fichier spécial appelé /dev/null et il rejettera toute entrée.

<pre>$ ls /fake/répertoire 2> /dev/null</pre>

## Exercice

Que fait la commande suivante ? 

<pre>$ ls /fake/directory >> /dev/null 2>&1</pre>

## Question d'interrogation

Quel est le redirecteur pour stderr ?

## Réponse au quiz

2>
