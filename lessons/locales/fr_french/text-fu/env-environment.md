# env (Environnement)

## Contenu de la leçon

Exécutez la commande suivante : 

<pre>$ echo $HOME</pre>

Vous devriez voir le chemin vers votre répertoire personnel, le mien ressemble à /home/pete. 

Qu'en est-il de cette commande ? 

<pre>$ echo $USER</pre>

Vous devriez voir votre nom d'utilisateur !

D'où vient cette information ? Elle provient de vos variables d'environnement. Vous pouvez les visualiser en tapant

<pre>$ env </pre>

Cela sort tout un tas d'informations sur les variables d'environnement que vous avez actuellement définies. Ces variables contiennent des informations utiles que le shell et d'autres processus peuvent utiliser.

Voici un court exemple :

<pre>
PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/bin
PWD=/home/user
USER=pete
</pre>


Une variable particulièrement importante est la variable PATH. Vous pouvez accéder à ces variables en collant un $ devant le nom de la variable comme suit :

<pre>
$ echo $PATH
/usr/local/sbin:/usr/local/bin:/usr/sbin:/bin
</pre>

Cela renvoie une liste de chemins séparés par deux points que votre système recherche lorsqu'il exécute une commande. Disons que vous téléchargez et installez manuellement un paquet depuis internet et le mettez dans un répertoire non standard et que vous voulez exécuter cette commande, vous tapez $ coolcommand et l'invite dit commande non trouvée. C'est idiot, vous regardez le binaire dans un dossier et vous savez qu'il existe. Ce qui se passe, c'est que la variable $PATH ne vérifie pas l'existence de ce binaire dans ce répertoire, ce qui entraîne une erreur. 

Imaginons que vous ayez des tonnes de binaires que vous voulez exécuter à partir de ce répertoire, vous pouvez simplement modifier la variable PATH pour inclure ce répertoire dans votre variable d'environnement PATH.


## Exercice

Quelle est la sortie suivante ? Pourquoi ?
<pre>$ echo $HOME</pre>

## Question d'interrogation

Comment voyez-vous vos variables d'environnement ?

## Réponse au quiz

env