# Aprendiendo Git con Jhon Mircha

indice:

> [Descripcion del curso](#descripcion-del-curso)
>
> [Comandos basicos para configuracion global](#comandos-basicos-de-configuracion-global)
>
> [Comandos basicos de flujo de Git](#comandos-basicos-de-flujo-git)
>
> [Utilizando Git con un proyecto de React dirigido a GitHub Pages](#utilizando-git-con-un-proyecto-de-react-dirigido-a-github-pages)

---

## Descripcion del Curso

Este proyecto tendra el contenido aprendido del curso de git **(un software de controlador de versiones)**

---

# Comandos basicos de git

## comandos basicos de configuracion global

```
git config --global user.name (name)

git config --global user.email (email)

git config --global core.editor (editor --wait)

git config --list
```

_estandarizacion entre sistemas operativos_

En windows

```
git config --global core.autocrlf true
```

En linux o MacOS

```
git config --global core.autocrlf input
```

---

## comandos basicos de flujo git

```
git init

git add (directorio)

git commit o git commit -m ("name")

git remote add origin (url)
```

**Al momento de levantar el proyecto en un hostin se especifica la rama o branch**

```
git push -u origin master
```

**Despues de haberse subido por primera vez utilizamos**

```
git push
```

para obtener los cambios de un proyecto que se hayan hecho de manera remota y no local

```
git pull
```

para cambios de la rama o branch

```
git branch -M (rama)
```

si se a creado un repositorio con una rama no deseada se puede reemplazar de rama e eliminar la rama anterior

ejecutando los siguientes comandos

respaldamos a una nueva rama creandola con

```
git branch -m (rama anterior) (nueva rama)
```

generamos un nuevo push a esa rama

```
git push -u origin (nueva rama)
```

cambiamos el HEAD del anterior a la nueva rama

```
git symbolic-ref refs/remotes/origin/HEAD refs/remotes/origin/(nueva rama)
```

desde las configuraciones de tu repositorio en el apartado de rama o branch cambiamos nuestra rama por default a la nueva rama, de esta manera al ejecutar el comando de eliminacion de la anterior rama que estaba tambien por default no retornara un error

comando para la eliminacion de rama o branch desde el remoto

```
git push origin --delete (anterior rama)
```

## para ayuda con la informacion de comandos podemos usar los siguientes comandos

para vizualizar desde la terminal

```
git (comando) -h
```

o desde los archivos de la documentacion de git ya instalados

```
git help (comando)
```

## para ignorar archivos

creamos un archivo en nuestro proyecto con el nombre **.gitignore** dentro de el colocamos los nombres de los archivos/carpetas que no se deseen pasar por un flujo basico de git ademas de poder utilizar expresiones regulares para especificar esos elementos.

## para clonar un repositorio

```
git clone (url del repositorio)
```

## Crear y moverse entre ramas

para crear una rama

```
git branch (nombre de la rama)
```

para cambiar de rama

```
git checkout (nombre de la rama)
```

para crear de rama y a la vez cambiarte a ella

```
git checkout -b (nombre de la rama )
```

## Enlistacion e eliminacion de ramas

para eliminar una rama

```
git branch -d (nombre de la rama)
```

para eliminar una rama de manera forzada

```
git branch -D (nombre de la rama)
```

para enlistar las ramas de tu repositorio

```
git branch
```

para enlistar ramas que aun no han sido fusionadas

```
git branch --no-merged
```

para enlistar ramas que hayan sido fucionadas

```
git branch --emerged
```

rebasar ramas

nos cambiamos a la rama que queremos rebasar

```
git checkout (rama-secundaria)
```

depues hacemos el rebasado con el siguiente comando indicando a la rama que se quiere rebasar

```
git rebase (rama principal )
```

## fusion de ramas

para una fusion de ramas

tenemos que posicionarnos en nuestra rama pricipal y ejecutar

```
git merge (rama que se quiere fusionar)
```

## Modificacion de commits

para editar el ultimo commit pero sin editar el mensaje

```
git commit --amend --no-edit
```

para editar el ultimo commit y el mensaje

```
git commit --amend -m "mesaje"
```

para resetear un commit

```
git reset --hard HEAD~1
```

para cambiar entre commits

```
git checkout (id-commit)
```

## Resgistro del historial

para ver el historial

```
git log
```

para ver el historial en una sola linea

```
git log --one-line
```

para guardar el historial en un archivo

```
git log > (nombre del archivo e extencion)
```

para mostrar historial con formato perzonalizado

```
git log --pretty=format:"%h - %an", %ar : %s"
```

para mostrar la cantidad que quieres de commits

```
git log -n (numero)
```

para colocar commits dentro de una fecha

despues de una fecha

```
git log --after="2022-09-01 00:00:00"
```

antes de una fecha

```
git log --before="2022-09-01 00:00:00"
```

en un intervalo de fechas

```
git log --after="2022-09-01 00:00:00" --before="2022-09-02 00:00:00"
```

para mas informacion del historial, incluyendo interacciones, cambios, fuciones, eliminaciones, etc

```
git reflog
```

para ver cambios entre el staging y el working directory

```
git diff
```

para ver graficas de fusiones

```
git log --oneline --graph --all
```

para guardar la grafica en un archivo

```
git log --oneline --graph --all > (nombre del archivo y extencion)
```

## Reseteo del historial

para saber el estado de los archivos

```
git status
```

para resetear el HEAD

```
git reset --soft
```

para resetear el HEAD y el staging

```
git reset mixed
```

para resetear todo staging, HEAD working directory

```
git reset --hard
```

para resetear commit con commit

```
git reset (commit-id)
```

para resetear un commit de manera dura

```
git reset --hard (commit-id)
```

## Resetear repositorio como si fuera nuevo\

respaldamos el archivo de configuracion con el siguiente comando

```
mv .git/config ~/saved_git_config
```

eliminamos la carpeta git con

```
rm -rf .git
```

iniciamos de nuevo git con los comandos de flujo basico de git

```
git init
```

agregamos el archivo respaldado de la configuracion

```
mv ~/saved_git_config .git/config
```

```
git branch -M rama

git add (files to add)

git commit -m (name of the commit)
```

ejecutamos un push de manera forzada

```
git push --force origin main
```

## Remotes

para mostrar los remotos

```
git remote
```

para ver los detalles del remoto

```
git remote -v
```

para agregar remotos

```
git remote add (name-origin) (url)
```

para renonbrar el origen

```
git remote rename (old-name)(new-name)
```

para remover el remoto

```
git remote remove (name-origin)
```

para descargar diferentes ramas del remoto

```
git checkout --track -b (remote-branch) origin/(remote-branch)
```

## Tags

para enlistar etiquetas

```
git tag
```

para crear una etiqueta

```
git tag (num of version)
```

pata eliminar una etiqueta

```
git tag -d (num of version)
```

para mostrar la informacion de la etiqueta

```
git show (num of version)
```

para hacer un push al remoto

hay dos maneras

la primera:

```
git add .
git tag "v1.0.1"
git commit -m "v1.0.1"
git push origin (num of version)
```

la segunda:

```
git add .
git tag -a "v1.0.1" -m "coomit con tags"
git push --tags
```

## git con github pages

primero creamos una rama llamada gh-pages

```
git branch gh-pages
```

y podemos subir nuestro codigo con un push

```
git push -u origin gh-pages
```

para descargar el repositorio

```
git pull origin gh-pages
```

## trabajar en colaboracion

-primero forkeamos el repositorio con el que tenemos que colaborar desde gitHub o otra plataforma de hostin

-despues lo clonamos con

```
git clone (url)
```

## para configurar un repositorio de manera local

```
git config --local user.name (name)

git config --local user.email (email)

git config --local core.editor (editor --wait)

```

## trabajar en colaboracion parte 2

para hacer cambios en el proyecto

renombramos el origin de nuestra copia

```
git remote rename (old-name) (new-name)
```

agregamos el remoto del repositorio global

```
git remote add origin (url)
```

creamos una nueva rama

```
git checkout -b (new-branch)
```

hacemos push al remoto de nuestra copia

```
git push -u (old-name) (new-branch)
```

solicitamos un pull request desde github

desde el repositorio principal se acepta el pull request

hacemos un pull desde el repositorio principal

desde el repositorio que hizo los cambios una vez aceptado eliminamos la rama donde se trabajo los cambios

ejecutamos los siguientes comandos

```
git checkout main
git pull origin main
git push (new-name) main
git branch -d (new-branch)
git push (new-name) --delete (new-branch)
```

# Utilizando Git con un proyecto de React dirigido a GitHub Pages

primero en nuestro proyecto de react tenemos que descargar gh-pages

```
npm install --save-dev gh-pages
```

agregamos la direccion de nuestro origen remoto del repositorio de gitHub

```
git remote add origin (direccion del repositorio)
```

ahora hay que hacer configuraciones en nuestro **_package.jon_**

para la direccion de nuestra pagina principal colocamos

```
"homepage": "https://(usuario github).github.io/(nombre del repositorio)",
```

en los scripts de nuestro **_package.jon_** colocar

```
  "predeploy": "npm run build",
  "deploy": "gh-pages -d build"
```

ejecutamos los comandos

```
npm run build
```

y despues

```
npm run deploy
```
