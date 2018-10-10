# Git en español

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