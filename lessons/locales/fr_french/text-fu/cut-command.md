## cut

## Contenu de la leçon

Nous allons apprendre quelques commandes utiles que vous pouvez utiliser pour traiter du texte. Avant de commencer, créons un fichier avec lequel nous allons travailler. Copiez et collez la commande suivante, un e fois que vous avez fait cela, ajoutez un TAB entre lazy et dog (maintenez enfoncé Ctrl-v + TAB).

<pre>$ echo 'The quick brown ; fox jumps over the lazy dog' > sample.txt</pre>

La première commande que nous allons apprendre est la commande cut. Elle extrait des portions de texte d'un fichier. 

Pour extraire le contenu par liste de caractères : 

<pre>$ cut -c 5 sample.txt</pre>

Cela sort le 5e caractère de chaque ligne du fichier. Dans ce cas, c'est "q", notez que l'espace compte également comme un caractère. 

Pour extraire le contenu par champ, nous allons devoir faire une petite modification : 

<pre>$ cut -f 2 sample.txt</pre>

Le -f ou argument field (champs) coupe le texte basé sur les champs, par défaut il utilise les TABs comme délimiteurs, donc tout ce qui est séparé par un TAB est considéré comme un champ. Vous devriez voir "dog" en sortie.

Vous pouvez combiner l'agument de champ avec l'argument de délimiteur pour extraire le contenu par un délimiteur personnalisé : 

<pre>$ cut -f 1 -d " ;" sample.txt</pre>

Cela changera le délimiteur TAB en délimiteur " ;" et puisque nous coupons le premier champ, le résultat devrait être "The quick brown".

## Exercice

Que fait la commande suivante ? Pourquoi ?

<pre>$ cut -c 5-10 échantillon.txt
$ cut -c 5- sample.txt
$ cut -c -5 échantillon.txt
</pre>

## Quiz Question

Quelle commande utiliseriez-vous pour obtenir le premier caractère de chaque ligne d'un fichier ?

## Réponse au quiz

cut -c 1