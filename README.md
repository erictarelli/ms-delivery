# ms-delivery

##CREAR NUESTROS ALIAS##
git config -global alias.lg "log --oneline --decorate --all --graph"
git config -global alias.s "status -s -b"

###COMANDOS UTILES###

git log --oneline --decorate --all --graph
git status -s -b

git diff ##listado de diferencias del comit con el local
git diff --staged ##Sirve para verificar todos los archivos que esten el stage
git diff rama-villanos master ##Diferencia entre ramas, rama-villanos y master

git config --global user.name "[]" ##Agrego informacion personal
git config --global user.email "[]" ##Agrego informacion personal
git config --global -e ##Listado de informacion personal cargados

git init ##Crear repositorio
git log ##Muestra todo el historial de commit
git status ##Muestra que se encuentra pendiente, y que cosas hay en el stage

git add . ##Agrega todos los archivos pendientes
git add [] ## Agrega al stage los archivos o carpetas
git add "*.txt" ##Agrega todos los txt del TODO el proyecto
git add *.txt ##Agrega todos los txt en el directorio actual
git add --all Agrega todos los archivos
git add <lista de archivos> Agrega los archivos listemos
git add -u ##Actualizar todo

git commit -m "[]" ## Se agrega un mensaje y se guarda el stage, seria como una captura de lo que ya esta echo 
git commit --amend -m "Actualizamos el readme" ## Revertir el titulo asignado al commit que realice
git commit -am "Actualizamos el README" ##Sirve para agregar al stage y agreger el commit

git checkout -- . ##Reconstruye todo el proyecto a partir del ultimo commit
git checkout -- README.md ## Restaura el archivo README
git checkout rama-villanos ##Para ir a la rama creada, rama-villanos.
git checkout -b rama-villano ##Crear una rama, y me muevo a ella. 

git mv destruir-mundo.txt salvar-mundo.txt ##Renombrar archivo

git rm salvar-mundo.txt ##Eliminar archivo

git reset HEAD README.md ##Para sacar del stage el archivo README
git reset *.xml ##Excluir de la lista de los stage
git reset --soft HEAD^ ##Sirve para actualizar el archivo README con el commit que habiamos generado. es el menos destructivo, no modifica ni destruye ni borra nada
git reset --soft 3ds23 ##Vuelvo a ese punto
git reset --mixed 
git reset --hard 1ds22 ##Vuelve a ese punto y destruye todos los posteriores

## COMANDOS PARA REGRESION DE EMERGENCIA 

git reflog ##Lista todos los commit por mas que se hayan eliminado con el comando HARD

##IGNORAR ARCHIVOS##

.gitignore ##Crear archivo para ignorar

##RAMAS##

Tendremos que estar en la rama en la cual nosotros queremos fusionar algo

git merge rama-villanos ##Mergea desde la rama master lo que haya en la rama rama-villanos

git branch #Lista los ramas creadas
git branch rama-villanos ## Creo una rama llamada rama-villanos
git branch -d rama-villanos ##Elimina la rama

1- fast-forward (Marge trasparentes)
2- uniones-automaticas (Marge en los puntos donde no se solapen el codigo modificado)
3- union-manual

##TAG##

git tag 0.1.0 ## Generar un tag
git tag ##Lista los tag
git tag -d 0.1.0 ##Eliminar tag 0.1.0
git tag -a 1.0.0 -m "Version 0.1.0" ##Generar la version con descripcion
git tag -a 0.0.a 345d6de -m "Version alfa" ##Genero version apartir de algun commit ya generado tiempo atras

git show 0.1.0 ##Ver descripcion del tag generado

##STASH##

Contenedor para poner todos los cambios temporales para dejarlo en un determinado commit

git stash ## Guarda lo que hayamos echo, y vuelve al ultimo commit
git stash list ##Muestra todos los trabajos que se estan trabajando
git stash pop ##Recupera los archivos y cambios del stash que hicimos.
git stash drop stash@{0} ##Elimina el stash de una posicion determinada 
git stash save --keep-index ##Guarda todo menos los archivos en el stage o en el secenario
git stash save --include--untracked ##Incluye todos los archivos, junto a los que git no le da seguimiento
git stash list --stat ## Muestra mas informacion de cada una  de las entradas del los stash
git show stash ## Muestra informacion de los cambios en las lineas de todo lo que se hizo en ese stash
git show stash@{1} ## Muestra informacion particular de ese stash
git stash save "Agregamos a loki en los villanos" ##Genera un stash con una descripcion
git stash clear ##Borra todos los stash, IMPORTANTE no hay forma de recuperarlo

##REBASE##

Sirve para rehacer cosas que ya hicieron previamente sin afectar la linea de tiempo

git checkout rama-misiones ## ejemplo me posicion en esta rama
git rebase  master ## Mueve todos los commit de la rama rama-misiones, a un area temporal. y luego mueve esos commits al ultimo commit del rama master

##REBASE INTERACTIVO ##

-ordenar commit
-gorregir mensajes de los commits
-unir commits
-separar commits

git rebase -i HEAD~3 ## 
git rebase master ## mueve la master el orden al final

##REBASE SQASH##

git rebase -i HEAD~4 ##Seleccion los ultimos 4 commit, order desc

##REBASE REWORD#

git rebase -i HEAD~1 #Sirve para editar el mensaje del commit rebase 

##REBASE EDIT##

git rebase -i HEAD~2 ##Para separa en dos commit los cambios

git reset HEAD^

git rebase --continue ##

## GIT HUB ##

git remote add origin https://git**** ##es origin es el nomnre del repositorio
git remote -v ## para chequear cuantas remotos tenemos

git push -u origin master ##
git push --tags ##Para subir los tags

git fetch ##No hace merge de forma automatica
