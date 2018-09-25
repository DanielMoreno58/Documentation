# Git en español

## GitIgnore

El archivo `.gitignore` indica los archivos que no serán subidos remotamente.

Si por alguna razón agregaste el .`gitignore` al inicio puedes ejecutar esta series de comandos para borrar todos los archivos que no están incluidos en el gitignore.

```
git rm -r --cached .
git add -A
git commit -m 'Removing ignored files'
```
Para más información da click [aquí](https://eric.blog/2014/05/11/remove-files-from-git-addingupdating-gitignore/).