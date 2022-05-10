# Comandos Git
>**git init:** :Inicia un repositorio en la carpeta de nuestro proyecto
>
>**git status:** Muestra el estado de los cambios y los archivos que han sido modificados o agregados 
>
>**git add:** añade archivos
>
>**git rm(nombre archivo)** Elimina los archivos de stage pero siguen en cache
>
>**git rm --cached (nombre archivo)** elimina por completo el archivo del stage y del repositorio local.
>
>**git rm --force:** Elimina los archivos de git y del disco curo
>
>**git config --global user.name**    Configuracion del nombre de usuario de git
>
>**git config --global user.email:** Configuracion del email del usuario de git
>
>**git log(nombre archivo):** Comando para ver el historial de todos los cambio hechos al archivo indicado.
>
>**git log --stat:** Muestra la cantidad cambios realizados en  los archivos.
>
>**git show:** Muestra los cambios a lo largo del tiempo en los archivos 
>
>**git diff (archivo1) (archivo2):** compara las versiones de los archivos atraves del id de los commits.
>
>**git reset --soft:** Borramos todo el historial y los registros de git pero guardamos los cambios que esten en staying.
>
>**git reset --hard:** Borra todo todito, absolutamente todo.
>
>**git checkout (id commit)(nombre archivo)** Nos regresa a una version anterior y podemos modificarla, borrarla y enviarla de nuevo al repositorio master.
>
>**git branch(Nombre rama)** Crea una nueva rama de trabajo.
>
>**git checkout (Nombre rama)** Este variacion del comando la usamos para movernos a diferentes ramas y regresar al ultimo comit de la rama a la cual estamos indicando.
> 
>**git merge (Nombre de la rama)** Fusiona dos ramas para unir cambios hechos a secciones diferentes del codigo. Casi siempre se hacen desde la rama master.
>
># Comandos para subir tu proyecto a GitHub
>
>**git remote add origin (Url de nuestro repositorio en Git)** Colocamos la url de nuestro repositorio de github.
>
>**git remote** Verificamos que la url se hay guardado.
>
>**git remote -v**  Verificamos que la url se haya guardado
>
>**git pull origin main --allow-unrelated-histories** Traemos la version del repositorio remoto y hacemos merge para crear un commit con los archivos de ambas partes(local y remoto).
>
>**git push origin master:main** Enviamos los cambios ya fusionados en local a nuestro repositorio remoto
>
>**git pull origin main** Traemos los cambios del repositorio remoto a nuestro repositorio local
>
># Cambio de la url de nuestro repositorio usando un protocolo https a un ssh
>
>**git remote -v** Verifica la url de nuestro repositorio
>
>**git remote set-url origin (url en ssh o https)** Modifica la url con la que nos conectamos a nuestro repositorio remoto.

# Manejo de Tags en Git

>**git log --all** Muestra todos los commits sin importar nada
>
>**git log --all --graph --decorate --oneline** Vista de arbol para tener un mejor panorama de los commits.
>
>**git tag -a (nombre, lo recomendado es v0.1) -m "comentario" (id del commit)** Creamos un nuevo tag.
>
>**git show-ref --tags** Muestra el listado de tags con mas detalle.
>
>**git push origin --tags** Enviar los tags al repositorio remoto.
>
>**git tag -d (nombre del tag)** Eliminar el tag en el repositorio local
>
>**git push origin :refs/tags/(nombre del tag)** Eliminar los tags en el repositorio remoto.
>
# Manejo de ramas

>**git show-branch** Ver las ramas.
> 
>**git show-branch --all** Ver todas las ramas con mas mas informacion.
>
>**git push origin (nombre de la rama)** Enviar ramas del repositorio local al remoto.
>
>**git branch -D (nombre de la rama)** Elimina una rama que ya no este en uso en el repositorio de trabajo local.
>
>**git push origin :(nombre de la rama)** Elimina una rama en el repositorio remoto.
>
# Pull Request

>**Pull request** es una funcionalidad de Github (en Gitlab llamada _merge request_ y en Bitbucket _push request_), en la que un colaborador pide que revisen sus cambios antes de hacer _merge_ a una rama, normalmente _master_ (ahora conocida como _main_).

>Al hacer un pull request, se genera una conversación que pueden seguir los demás usuarios del repositorio, así como autorizar y rechazar los cambios. 
