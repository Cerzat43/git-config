# Git alias

*Quelques alias pour faciliter l'utilisation de git en ligne de commande*

---

## Mettre en place les alias sous Ubuntu

Les alias sont dans le fichier `.gitalias` à la racine du dépôt.
Pour installer ces alias, copiez-collez simplement le contenu de ce fichier dans `~/.gitconfig`.

Sous git 1.7.10+ (`git --version`), il est possible de placer ce fichier dans `~/.gitalias`
et ajoutez cette ligne dans le fichier `~/.gitconfig` :

```bash
[include]
path = .gitalias
```

Il est aussi possible de faire un alias pour `git` (dans mon cas, `g`) de manière classique (par exemple en l'ajoutant dans votre `~/.bashrc`).
Dans ce cas, il faudra ajouter quelques lignes pour faire fonctionner l'autocomplétion de git avec l'alias :

```bash
# alias git -> g
alias g='git'

# à décommenter sous Ubuntu 13.04+
# source /usr/share/bash-completion/completions/git

complete -o bashdefault -o default -o nospace -F _git g 2>/dev/null || complete -o default -o nospace -F _git g
```

## Liste des alias

```bash
# git add
git a
```

```bash
# !git config -l | grep ^alias. (Liste les alias git)
git alias
```

```bash
# git commit --amend
git amend
```

```bash
# git branch
git b
```

```bash
# git commit
git c
```

```bash
# git checkout
git co

# git checkout -b
git cob
```

```bash
# git cherry-pick
git cp
```

```bash
# git diff --color
git d
```

```bash
# git branch --no-merged dev (fonctionnalités En Développement)
git ed
```

```bash
# git fetch
git f
```

```bash
# git gui
git g
```

```bash
# gitk --all
git k
```

```bash
# git log --all --graph --abbrev=5 --pretty=tformat:'%C(yellow)%h%Creset -%C(green bold)%d%Creset %s %C(white dim)(%cr) %C(blue bold)<%an>%Creset' --abbrev-commit
git lg

# git --no-pager lg (Affiche tous les logs sans pagination, utile pour `grep`)
git lgnp

# !"f() { if [ -z \"$1\" ]; then lc=\"20\"; else lc=$1; fi; git lgnp | head -n \"$lc\"; }; f"
# (Affiche les 20 premières lignes de log : LoG Head)
git lgh
# utilisation :
g lgh
# ou (pour les n premières lignes):
g lgh n
```

```bash
# git merge --no-ff -e (no fast forward avec message de commit)
git m
# utilisation :
g m to-merge-branch

# git merge
git mff
```

```bash
# git mergetool -y (sans confirmation)
git mt
```

```bash
# git push
git p
```

```bash
# git pull
git pl
```

```bash
# git rebase
git rb
```

```bash
# git status
git s
```

```bash
# git stash
git st

# git stash list
git stl

# git stash apply
git sta

# git stash drop
git std

# git stash show -p
git sts

# git stash pop
git stp
```

```bash
# git reset --soft HEAD^ (Annuler un commit)
git unc
```

```bash
# git shortlog -sne (Nombre de commits par contributeur)
git who
```