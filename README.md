# Aprendiendo Git con Jhon Mircha

indice:

> [Descripcion del curso](#descripcion-del-curso)
>
> [Comandos basicos para configuracion global](#comandos-basicos-de-configuracion-global)
>
> [Comandos basicos de flujo de Git](#comandos-basicos-de-flujo-git)

## Descripcion del Curso

Este proyecto tendra el contenido aprendido del curso de git **(un software de controlador de versiones)**

## Comandos basicos de git

### comandos basicos de configuracion global

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

En linux o Mac Ox

```
git config --global core.autocrlf input
```

### comandos basicos de flujo git

```
git init

git add (directorio)

git commit o git commit -m ("name")

git remote add origin (url)
```

**Al momento de levantar el proyecto en un hostin se especifica la rama p branch**

```
git push -u origin master
```

**Despues de haberse subido por primera vez utilizamos**

```
git push
```
