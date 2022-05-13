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

# Archivos .gitignore dentro de un  repositorio

>No todos los archivos que agregas a un proyecto deberían ir a un repositorio. Por ejemplo, cuando tienes un archivo donde están tus contraseñas que comúnmente tienen la extensión  `.env`  o cuando te estás conectando a una base de datos;  **son archivos que nadie debe ver**.

>Por diversas razones, no todos los archivos que agregas a un proyecto deberían guardarse en un repositorio. Esto es porque hay archivos que no todo el mundo debería de ver, y hay archivos que al estar en el repositorio ralentizan el proceso de desarrollo (por ejemplo: los binary large objects, blob, que tardan en descargarse).

>Para que no se suban estos archivos no deseados se puede crear un archivo con el nombre .gitignore en la raíz del repositorio con las reglas para los archivos que no se deberían subir: Aquí puedes ver la  [sintaxis de los .gitignore](https://git-scm.com/docs/gitignore).

>Las razones principales para tomar la decisión de no agregar un archivo a un repositorio son:

>-   Es un archivo con contraseñas (normalmente con la extensión .env)
>-   Es un blob (binary large object, objeto binario grande), mismos que son difíciles de gestionar en git.
>-   Son archivos que se generan corriendo comandos, por ejemplo la carpeta node_modules, que genera  **npm**  al correr el comando npm install.

# Stash en git 

>El _stashed_ nos sirve para guardar cambios para después, Es una lista de estados que nos guarda algunos cambios que hicimos en Staging para poder cambiar de rama sin perder el trabajo que todavía no guardamos en un commit

>**git stash** agrega los cambios al stash 
>
>**git stash save "Mensaje identificador"** Guarda en el stash agregando un mensaje.
>
>** git stash pop** Recupera los cambios de stash al staging.
>
>**git stash pop stash@{<num_stash>}** Para aplicar los cambios de un stash específico y eliminarlo del stash.
>
>**git stash list** Ver la lista de los stash
>
># Crear una rama con un stash
>
>**git stash branch "<nombre_de_la_rama>** Crea una rama con un stash.
>
>**git stash branch nombre_de_rama stash@{<num_stash>}**  crea una rama y aplicar un stash específico (obtenido desde `git stash list`).
>
># Eliminar elementos del stash

>**git stash drop** Elimina los cambios mas recientes dentro del stash.
>
>**git stash drop stash@{<num_stash>}** Borra un stash especifico.

# Comando git clean

>El comando `clean` actúa en archivos sin seguimiento, este tipo de archivos son aquellos que se encuentran en el directorio de trabajo, pero que aún no se han añadido al índice de seguimiento de repositorio con el comando `add`.

>**git clean --dry-run** Es un borrado en falso, únicamente funciona en archivos que aun no han sido traqueados. El resultado es una lista de archivos
> 
>**git clean -f** Elimina los archivos del comando anterior.
>
>Git clean tiene muchísimas opciones adicionales, que puedes explorar al ver su [documentación oficial](https://git-scm.com/docs/git-clean).
>
# Comando cherry-pick 

>Este comando es una mala practica, se debe de tener mucho criterio para poder utilizarlo. Lo mejor siempre sera el comando merge de todo la vida y solucionar todos los conflictos que este pueda presentar.

>**git cherry-pick <numero_de_commit>** Trae un fragmento de una rama a otra.

# Comandos usados en casos de emergencia

>Estos comandos son una mala practica, al momento de ser usados se debe de conocer con exactitud lo que se esta haciendo para no hacer un daño catastrófico al proyecto.

>**git reflog** Este comando muestra un listado de todos los registros de referencia.

>¿Qué pasa cuando todo se rompe y no sabemos qué está pasando? Con `git reset HashDelHEAD` nos devolveremos al estado en que el proyecto funcionaba.

>**git reset --soft <ref_commit>** Mantiene lo que esta en staging.
>
>**git reset --hard <ref_commit>** Resetea absolutamente todo incluyendo lo que esta en el staging.
>
# Remendar los commits

>_Remendar_ un commit con `amend` puede modificar el commit más reciente (enmendar) en la misma rama. Lo ejecutamos así:
>
>**git add -A** Para hacer uso de amend los archivos deben de estar en staging. 
>
**git commit --amend** Remendar último commit

## **Atención**

Usar  `amend`  es una **mala práctica**, sobre todo cuando ya se ha hecho **push o pull** al repositorio remoto. Al momento de hacer amend con algún `commit` que esté en remoto, va a generar un **conflicto** que se va a arreglar haciendo un `commit adicional` y se **perderá el beneficio** del amend.

# Búsqueda de elementos en nuestro proyecto 

>**git grep (palabra)** Busca una palabra especifica dentro de los archivos del proyecto.
>
>**git grep -n (palabra)** Nos saldrá un output el cual nos dirá en qué línea está lo que estamos buscando.
>
>**git grep -c (palabra)** Nos saldrá un output el cual nos dirá cuántas veces se repite esa palabra y en qué archivo.
>
>**git grep -c "(etiqueta HTML)"** Nos saldra un output el cual dira cuantas veces se repite dentro de un archivo HTML.
>
>**git log -S (palabra)** Busca en el historial de logs de nuestro repositorio.
>
# Comandos y recursos colaborativos en Git y GitHub

>`git shortlog -sn:` muestra cuantos commit han hecho cada miembro del equipo.
>
>`git shortlog -sn --all`: muestra cuantos commit han hecho cada miembro del equipo, hasta los que han sido eliminados.
>
>`git shortlog -sn --all --no-merge`: muestra cuantos commit ha hecho cada miembro, quitando los eliminados sin los merges.
>
>`git blame ARCHIVO`: muestra quien hizo cada cosa línea por línea.
>
>`git blame ARCHIVO -Llinea_inicial,linea_final`: muestra quien hizo cada cosa línea por línea, indicándole desde qué línea ver. Ejemplo -L35,50.
>
>`git branch -r`: se muestran todas las ramas remotas.
>
>`git branch -a`: se muestran todas las ramas, tanto locales como remotas.

*>@Autor : `Carlos Rodriguez`*
