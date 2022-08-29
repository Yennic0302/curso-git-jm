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

git comit o git comit -m ("name")

git push (directorio)
```
