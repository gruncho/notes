# Git

Copypaste notas @mktoast:

## Email git

```
$ git config --global user.email "email@example.com"
```

## Actualizar rama. Pull + rebase

```
git pull origin master --rebase
```

## Revertir cambios en un fichero

```
git checkout -- component.html.twig
```

## Eliminar rama en local

```
git branch -D fix/variant-selector 
```

## Revertir último commit (no pusheado)

```
git reset --soft HEAD^
```
(--soft devuelve los cambios al stage)
(--hard se calza los cambios)

Se pueden revertir múltiples commits con HEAD~n (donde n es el número de commits a revertir). Mejor tirar el comando previo múltiples veces...


## Rebase en la rama 

Metemos los cambios de master, por ejemplo, en la rama feature/component.

Importante tener la rama, en este caso master, actualizada)

```
git checkout master
git pull origin master --rebase
```
(nos aseguramos de que está actualizada)
```
git checkout feature/componente
git rebase master
```
(y forzamos el push con -f) // Cuidado con forzar los pushes, porque modifican el histórico. Si hay más gente trabajando en la misma rama evitar hacer rebases.
```
git push origin feature/componente -f
```

## Corregir mensaje del commit

```
git commit "mensaje nuevo" --amend
```

## Otros recursos

· [git-blame-someone-else](https://github.com/jayphelps/git-blame-someone-else)
