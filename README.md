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
