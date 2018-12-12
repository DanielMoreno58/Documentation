# Git en español

Idiomas: [Español](https://github.com/danielmoreno58/documentation/tree/master/Git/README.es.md), [Inglés](https://github.com/danielmoreno58/documentation/tree/master/Git/README.md)

## Configuración de usuario

git config --global user.email "email@example.com"

## Agregar SSH Key localmente

1. Crear una carpeta llamada .ssh donde quieres guardar tu llave ssh

2. Crear tus archivos ssh con el comando:

`ssh-keygen -t rsa -b 4096 -C "correogit@dominio.com"`

3. Ingresar nombre de archivo

4. Ingresar frase secreta pra nuestro ssh

5. Crear un archivo llamado config

En ese archivo guardar la siguiente configuración:

```
Host *
 AddKeysToAgent yes
 UseKeychain yes
 IdentityFile ~/.ssh/nombre_de_archivo
```

6. Agregar el ssh a nuestro agente con el comando:

`ssh-add -K ~/.ssh/nombre_de_archivo`

## Agregar SSH Key en Github

1. Copiar el contenido del archivo ssh con la extensión.pub con el siguiente comando:

`pbcopy < ~/.ssh/nombre_de_archivo`

2. Ir al apartado de Settings > SSH and GPG keys

3. Hacer click en **New SSH Key**

4. Agregar nombre de nuestra ssh key referente a nuestro equipo de computo

5. Pegar el contenido del archivo ssh que copiamos en el paso 1.

6. Guardar ssh key.

## GitIgnore

El archivo `.gitignore` indica los archivos que no serán subidos remotamente.

Si por alguna razón agregaste el .`gitignore` al inicio puedes ejecutar esta series de comandos para borrar todos los archivos que no están incluidos en el gitignore.

```
git rm -r --cached .
git add -A
git commit -m 'Removing ignored files'
```
Para más información da click [aquí](https://eric.blog/2014/05/11/remove-files-from-git-addingupdating-gitignore/).

## Lista de comandos Git:

|        Comando         |                     Explicación                      |    Comentarios adicionales     |
| ---------------------- | ---------------------------------------------------- | ------------------------------ |
| `git checkout`         | Te mueve de branch entre git                         |                                |
| `git checkout -b`      | Crea una nueva branch y te mueve en git              |                                |
| `git branch`           | Te muestra las branch disponibles                    |                                |
| `git branch -d "nombre"` | Borra una rama que selecciones                     |                                |
| `git branch -m <nuevonombre>` | Renombra una branch en local                  |                                |
| `git add .`            | Agrega todos los archivos locales de tu pc/mac       |                                |
| `git commit -m "dm_funcionalidad"` | Realiza un commit con un comentario donde agregas tus iniciales y la funcionalidad que estas trabajando. |                                |
| `git commit --amend`   | Hace cambios en un commit anterior                   | Después de hacer commit abajo se tiene que hacer un push forzado para actualizar la información de arriba |
| `git commit --amend -m "nuevo nombre"` | Hace cambios en un commit anterior del nombre | Después de hacer commit abajo se tiene que hacer un push forzado para actualizar la información de arriba |
| `git push origin "branch"` | Sube la branch seleccionada a github             |                                |
| `git pull origin branch` | Obtiene la información de github y la sincroniza con tu computadora |                                |
| `git tag "nombre"`     | Agrega un tag, generalmente para una nueva versión   |                                |
| `git push origin "nombreTag"` | Sube el tag a github |                                |
| `git log`              | Muestra el log de lo realizado en git                |                                |
| `git log --oneline`    | Muestra todos cambios de commits, tags, merge y ramas de Git |                                |
| `git show "hash number"` | Muestra los cambios realizados de un commit especifico dando como referencia un hash number obtenido de log --oneline |                                |
| `git whatchanged`      | Muestra los últimos cambios que se realizaron en GitHub |                                |
| `git stash`            | Guarda la información de los cambios agregados a una pila para moverte entre branches sin traerte la información |   |
| `git stash pop`        | Saca la información guardada en una pila donde guardaste cambios anteriormente |      |
| `git stash list`       | Muestra la lista de todos los stash creados          |                                |
| `git stash clear`      | Borra todos los stash y sus contenidos               |                                |
| `git merge "branch"`   | Hace un merge de una branch a otra                   |                                |
| `git remote -v`        | Muestra todas los accesos remotos que se tienen de git |                              |

## Lista de comandos peligrosos Git:

|        Comando         |                     Explicación                      |    Comentarios adicionales     |
| ---------------------- | ---------------------------------------------------- | ------------------------------ |
| `git revert`           | Revierte el ultimo commit realizado                  |                                |
| `git reflog`           | Muestra todos los comandos que se ejecutaron en git  |                                |
| `git reset 'HEAD@{1}'` | Regresa a un comando que ejecutaste en git           |                                |
| `git reset --soft HEAD~1` | Regresa al commit anterior |                                |
| `git reset --hard 0d1d7fc32` | Regresa a un commit especifico indicando el hash del commit que se desea regresar |
| `git rebase "branchParaCopiar"` | Copia todos los commits de un branch en otro. Tener mucho cuidado con este comando ya que sobre escribe la información de un branch |                                |
| `git push origin "branch" -f` | Realiza un push de manera forzada | Tener cuidado con este comando porque puede sobre escribir información |
| `git checkout -- . `   | Borra todos los archivos que modificaste antes de hacer un commit | Tener cuidado con este comando porque no se recupera la info |
| `git clean -fdx` | Hace una limpieza de todos archivos de que ignora integra git | Tener mucho cuidado con ese comando porque no se recuperan los archivos |

## Referencias

Git reflog y reset 'HEAD@{1}': [Pregunta stackoverflow](https://stackoverflow.com/questions/2510276/undoing-git-reset)