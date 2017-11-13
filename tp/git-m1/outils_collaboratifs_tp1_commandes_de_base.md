Les commit dans git contienne votre nom et mail, ce sera important pour le TP2

Pour démarrer un nouveau dépôt, utiliser `git init`, puis `cd` pour entrer dans le répertoire créé par git.

Utiliser `echo` pour créer 3 nouveaux fichiers avec comme contenu une ligne "Ligne 1"

Avec `git status`, git vous montre qu'il y a 3 nouveaux fichier dans votre répertoire de travail qui sont "untracked" ou inconnu.

```
Pour ajouter ces fichiers au "staging", il faut utiliser la commande `git add`. Attention: cela n'ajoute pas le fichier à git, pour se faire il faut faire un "commit".

La commande `git status` vous montre l'état de votre dépôt

```bash
```
Le "staging" est la partie notée par "changes to be commited". Pour créer un nouveau commit, utiliser la commande `git commit`. À partir du moment ou un fichier est dans un commit, il est persisté à jamais dans git.

```bash
**TODO:** Ajouter fichier2 et fichier3 dans un 2e commit, jusqu'à ce que git affiche "working tree clean", ce qui veut dire que le dépôt git contient tous les fichiers qui sont dans votre répertoire de travail.
Vous avez déjà fait 2 commits et la commande `git log` vous permet de les voir

L'option `--name-status`` donne le contenu des commits (soit les fichiers qui sont dedans)

La commande `git show` permet de voir le contenu des modifications, les lignes ajoutées sont préfixées d'un +, les lignes supprimées sont préfixées d'un - (ce sont les seules modifications possibles)

Le paramètre HEAD veut dire "commit courant"

La syntaxe `HEAD~1` permet de revenir un commit en arrière (HEAD est le commit courant, HEAD~1 est le commit précédent, HEAD~2 est le commit d'avant, etc.)

# On branch master
# Changes not staged for commit:
#   (use "git add <file>..." to update what will be committed)
#   (use "git checkout -- <file>..." to discard changes in working directory)
# 
# 	modified:   fichier1
# 	modified:   fichier2
# 
# no changes added to commit (use "git add" and/or "git commit -a")
```

```bash
# diff --git a/fichier1 b/fichier1
# index 1aafa9c..304294e 100644
# --- a/fichier1
# +++ b/fichier1
# @@ -1 +1,2 @@
#  Ligne 1
# +Ligne 2
# diff --git a/fichier2 b/fichier2
# index 1aafa9c..304294e 100644
# --- a/fichier2
# +++ b/fichier2
# @@ -1 +1,2 @@
#  Ligne 1
# +Ligne 2
```

```bash
# [master 59c88f8] Mon 3e commit
#  1 file changed, 1 insertion(+)
Utiliser `git checkout` pour récupérer la dernière version d'un fichier (si le fichier est modifié, on revient à la version du dernier commit)

# Ligne 1
# Ligne 2


# Ligne 1
```

Utiliser `git revert` pour créer un commit qui est l'inverse du commit (les lignes ajoutées seront enlevées et vice-versa)

```bash
# fichier1  fichier2  fichier3  poubelle

# [master 3012558] poubelle
#  1 file changed, 0 insertions(+), 0 deletions(-)
#  create mode 100644 poubelle

# [master b010b1b] Revert "poubelle"
#  1 file changed, 0 insertions(+), 0 deletions(-)
#  delete mode 100644 poubelle

# commit b010b1b337739fdb644e0161ebaba0e8de78f34f
# Author: Alexandre DuBreuil <adu@lesfurets.com>
# Date:   Mon Nov 13 17:56:06 2017 +0100
# 
#     Revert "poubelle"
#     
#     This reverts commit 301255866e8f06f12fad3e709e5f8e63076e7bc4.
# 
# commit 301255866e8f06f12fad3e709e5f8e63076e7bc4
# Author: Alexandre DuBreuil <adu@lesfurets.com>
# Date:   Mon Nov 13 17:55:38 2017 +0100
# 
#     poubelle
# 
# commit 59c88f86b6b64c6f016bb6e078d520d89826dfb7
# Author: Alexandre DuBreuil <adu@lesfurets.com>
# Date:   Mon Nov 13 17:41:17 2017 +0100
# 
#     Mon 3e commit
# 
# ...

# fichier1  fichier2  fichier3
```

Utiliser `git reset` pour supprimer le commit. 

```bash
# HEAD is now at 3012558 poubelle

fichier1  fichier2  fichier3  poubelle
```

On est de retour sur le commit avec le fichier "poubelle"

```bash
# HEAD is now at 59c88f8 Mon 3e commit

#commit 59c88f86b6b64c6f016bb6e078d520d89826dfb7
#Author: Alexandre DuBreuil <adu@lesfurets.com>
#Date:   Mon Nov 13 17:41:17 2017 +0100
#
#    Mon 3e commit
# ...
On est bien revenu sur le 3e commit
