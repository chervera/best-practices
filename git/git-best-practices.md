# Buenas prácticas para la utilización de repositorios GIT y comandos que debes conocer

## Glosario GIT

### :bank: - **staging area**

## Procesos a seguir

### :snowflake: - Commit

1.  **git status** - Comprobar que lo que hay modificado es lo que realmente queremos modificar.
1.  **git add [ficheros]** - Hay que añadir los ficheros que queramos poner en el commit, si alguno esta modificado, pero no queremos que esté en el commit, no hay que añadirlo.
1.  **git commit -m [issue + '-' + mensaje]** - :bangbang: - Es importante poner un mensaje esclarecedor para identificar los commits a posteriori.
1.  :bangbang: - Revisar los logs que hayan salido ya que puede ser que git nos proponga algo o incluso que quede el commit sin hacer.

### :arrows_clockwise: - Actualizar mi código

1.  Ejecutar **git pull**. Si los ficheros que se han modificado en remoto coinciden con los modificados nuestros, será obligatorio hacer un [commit](#-snowflake-commit) de nuestros cambios primero (aunque no los subamos).
1.  Solucionar conflictos si es necesario.
1.  Hay que tener en cuenta que tendremos un nuevo [commit](#-snowflake-commit) en nuestro repositorio (no en el remoto) con la mezcla de lo de la rama remota y nuestros cambios locales.

### :thumbsup: - Subir Cambios

1. [Actualizar el código](#-arrows_clockwise-actualizar-mi-c-digo), por si hay cambios nuevos.
1. Seguir los pasos para hacer un [commit](#-snowflake-commit) con nuestros cambios.
1. **git push**
1. :bangbang: - Revisar los logs que hayan salido ya que puede ser que git nos proponga algo o incluso que quede el commit sin hacer.

### :fire_engine: - Cambiar de rama (con código sin terminar)

1. **git stash** - Con esta instrucción nuestro codigo modificado se moverá a un "limbo" y nos quedaremos como si estubieramos en el último commit que tengamos.
1. **git checkout [nombre-de-la-rama]** - vamos a la rama que necesitemos y hacemos todo lo que tengamos que hacer.
1. **git stash pop** - Copiamos los cambios que teniamos en el "limbo" en nuestra area de trabajo otra vez. [+ info sobre stash](https://git-scm.com/docs/git-stash)

### :checkered_flag: - Empezar una issue

TODO:

### :rocket: - Hacer un pull request

TODO:

## Comandos que debes conocer

1. :heavy_plus_sign: - **add [nombre-de-fichero]**

Con git **add** se añade el fichero especificado ( con . se añaden todos los ficheros) al staging area. Se debe hacer siempre antes de hacer un commit, si no, nada se añadirá al commit.

1. :camera: - **commit**

Ejecutando un **commit** lo que hacemos es crear un registro en **TU** repositorio con los cambios que queremos persistir. A posteriori se puede mandar al repositorio remoto.
