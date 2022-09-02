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

comando para la eliminacion de rama o branch

```
git push origin --delete (anterior rama)
```

### para ayuda con la informacion de comandos podemos usar los siguientes comandos

para vizualizar desde la terminal

```
git (comando) -h
```

o desde los archivos de la documentacion de git ya instalados

```
git help (comando)
```

### para ignorar archivos

creamos un archivo en nuestro proyecto con el nombre **.gitignore** dentro de el colocamos los nombres de los archivos/carpetas que no se deseen pasar por un flujo basico de git ademas de poder utilizar expresiones regulares para especificar esos elementos.

### para clonar un repositorio

```
git clone (url del repositorio)
```

## Manejo de ramas

### para crear una rama

```
git branch (nombre de la rama)
```

### para cambiar de rama

```
git checkout (nombre de la rama)
```

### para crear de rama y a la vez cambiarte a ella

```
git branch -b (nombre de la rama )
```

### para eliminar una rama

```
git branch -d (nombre de la rama)
```

### para eliminar una rama de manera forzada

```
git branch -D (nombre de la rama)
```

### para enlistar las ramas de tu repositorio

```
git branch
```

### para enlistar ramas que aun no han sido fusionadas

```
git branch --no-merged
```

### para enlistar ramas que hayan sido fucionadas

```
git branch --emerged
```

### rebasar ramas

nos cambiamos a la rama que queremos rebasar

```
git checkout (rama-secundaria)
```

depues hacemos el rebasado con el siguiente comando indicando a la rama que se quiere rebasar

```
git rebase (rama principal )
```

### para una fusion de ramas

tenemos que posicionarnos en nuestra rama pricipal y ejecutar

```
git merge (rama que se quiere fusionar)
```

### para editar el ultimo commit pero sin editar el mensaje

```
git commit --amend --no-edit
```

### para editar el ultimo commit y el mensaje

```
git commit --amend -m "mesaje"
```

### para resetear un commit

```
git reset --hard HEAD-1
```

### para cambiar entre commits

```
git checkout (id-rama)
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
