# comandos-comunes-git-

Esta es una lista de comandos útiles para git para desarrolladores de operaciones y búsquedas rápidas.


Repo público .tar para versiones de descarga:
[https://www.kernel.org/pub/software/scm/git/](https://www.kernel.org/pub/software/scm/git/)

** Eliminar con git todos los archivos enumerados como eliminados: **

$ git rm $(git ls-files --deleted)


** Eliminar una rama ABAJO en el repositorio local: **

$ git branch [branch name] --delete


** Eliminar una rama ARRIBA en el repositorio de servicios: **

$ git push origin --delete [branch name]


** No rastree los cambios en un archivo específico: **

$ git update-index --assume-unchanged [file]


** Realizar un seguimiento de los cambios de nuevo: **

$ git update-index --no-assume-unchanged


** Lista de archivos rastreados ocultos: **

$ git ls-files -v | grep '^[[:lower:]]'


** Limpiar el caché cuando git ignore falla (opciones): **

$ git rm -r --cached . 
$ git add . 
$ git commit -m "Fixed untracked files"


** Clonar un repositorio especificando la rama: **

$ git clone -b <branch> <myproject>.git


** Ignorar el cambio de archivo de modo, configurando git: **

$ git config core.fileMode false


** git checkout, no funciona ... posibilidades: **

$ git config --global core.autocrlf false
$ vim .gitattributes # comment line "* text=auto"


** Configurando git color: **

$ git config --global color.ui true


** Revertir una confirmación: **

$ git reset --soft 'HEAD^'


** Descartar la última confirmación: **

$ git reset HEAD --hard
$ git reset --hard origin/master

$ git reset --soft HEAD~1


** Fusionar conflictos (aceptar el suyo): **

$ git checkout --theirs


** Fusión de conflictos (acepta el nuestro): **

$ git checkout --ours


** Quitar un control remoto: **

$ git remote rm <remote>


** Resuelva el problema con la secuencia CRLF: **

$ git diff --ignore-space-at-eol


** Agregue archivos de seguimiento al escenario: **

$ git add -u .


** Revertir los cambios en un archivo específico confirmado y comenzar de nuevo: **

$ git checkout commit-reff~1 -- <file name>


** Elimine la última confirmación y establezca el cambio en "Cambiado pero no actualizado": **

$ git reset HEAD~1


** Exportar un proyecto "limpio": **

$ git archive master | tar -x -C </somewhere/else>
$ git archive master | bzip2 > <source.tar.bz2>
$ git archive --format zip --output <zipfile.zip> master

** Nota: ** Este es un sinónimo de svn export. Lo que hace es exportar y comprimir un repositorio sin ningún archivo .git *.

** Eliminando archivo de todo el historial: **

[https://help.github.com/articles/remove-sensitive-data/](https://help.github.com/articles/remove-sensitive-data/)

** Configuración de ignorar global **

$ git config --global core.excludesfile ~/.gitignore_global


** Bastante registro de git **

$ git log --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit

Alias * git lg *:

$ git config --global alias.lg "log --color --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit"


** Apague la advertencia CRLF **

git config core.safecrlf false


** Cambiar dominio para clonar ** (bower)

$ git config --global url."https://".insteadOf git://


** Publicar en páginas de github **

$ git subtree push --prefix <my site folder> origin gh-pages


