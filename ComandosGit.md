# COMANDOS GIT

## COMANDOS DE CONFIGURACION ENTORNO GIT

**Veremos la configuracion de entornos de git**

*Comandos para el establecimiento global del usuario y el email*

    git config --global user.name "<Nombre de Usuario>"
    git config --global user.email "<Email del Usuario>"

*Comandos para el establecimiento local del usuario y el email, para establecer diferentes emails para repositorios especificos*

    git config user.email "<Email del Usuario>"

*Si se es de windows se tiene que configurar *
 
    git config --global core.autocrlf true 

*Colocar VS Code Studio como editor de texto por defecto*

    git config --global core.editor "code --wait"

*Para ver las opciones de configuracion*

    git config -h

*Si queremos ver nuestro archivo de configuracion global escribimos lo siguiente*
    
    git config --global -e


## INICIALIZACION DE PROYECTOS CON GIT  

**Veremos los pasos para incializar proyectos**

*Para la inicializacion de proyectos git, usaremos el siguiente comando dentro de  la carpeta*

    git init

*Para clonar proyectos en repositorios remotos usaremos*

    git clone <URL_del_repositorio>


**Veremos las formas de usar git fetch**

*Para verificar si hay cambios para traerlos a la copia local del repositorio, pero sin fusionarlos usaremos(Tmabien trae informacion de las ramas remotas)*

    git fetch

*Se puede especificar la rama remota de la que queremos traer los cambios*

    git fetch origin <nombre_rama_remota>

*Se puede ver los cambios traidos con git fetch y ver si queremos combinar los cambios*

    git log

**Veremos las formas en las que se puede usar git pull**

*Para traer los cambios del repositorio remoto(Es decir un fetch), pero ademas las fusione automaticamente con la copia local usaremos*

    git pull

*Para trer los cambios de una rama remota especifica y fusinarlos con la rama local usaremos*

    git pull <nombre_repositorio_remoto> <rama_remota>:<rama_local>


**Veremos las opciones que tenemos con el comando git diff**

*Para ver los cambios sin preparar usaremos(sin añadir al area de staging)(Tambien se puede usar despues de git fetch para ver las diferencias entre ramas remotas y ramas locasles antes de fusionarlas)*

    git diff

*Para ver los cambios preparados usaremos(añadidos al area de staging)*

    git diff --staged

*Se puede comprobar las diferencias entre dos commits especificos*

    git diff <commit_hash_1> <commit_hash_2>

*Se puede comparar cambios entre dos ramas*

    git diff <rama_actual> <otra_rama>

*Se puede ver los cambios de un archivo especifico*

    git diff <archivo>

*Se puede ver los cambios en un directorio especifico*

    git diff <ruta_del_directorio>


## PREPARACION PROYECTOS GIT

**Comandos para controlar las ramas con git branch**

*Para ver la lista de las ramas en el repositorio usaremos*

    git branch

*Crear una nueva rama*

    git branch <nombre_nueva_rama>

*Cambiar a una rama existente*

    git checkout <nombre_rama>

*Eliminar una rama ( Esto solo funcionara si la rama se ha fusionado con otra rama)*

    git branch -d <nombre_rama>

*Si deseamos formas la eliminacion de la rama usaremos*

    git branch -D <nombre_rama>

*Renombrar una rama*

    git branch -m <nuevo_nombre> 

**Formas de usar git checkout para interactuar correctamente con las ramas**

*Cambiar a una rama existente* 

    git checkout <nombre_rama>

*Crear y cambiara a una nueva rama*

    git checkout -b <nombre_nueva_rama>

*Crear una rama a partir de un commit y cambiar a ella*

    git checkout -b <nombre_nueva_rama> <hash_commit>

*Si hemos realizado cambios en un archivo pero queremos descartar esos cambios y volver al estado del último commit*

    git checkout -- <nombre_archivo>

*Si hemos agregado cambios al area de stagin y queremos quitarlos y volver al estado anterior usaremos*

    git checkout -- <nombre_archivo>

**Para ver el estado actual del proyecto en sus diferentes estados en relacion con el repositorio GIT**

*Para ver el estado*

    git status

*Para ver el estado de una manera mas detallada*

    git status -s

*Para ver el estado de las ramas y tambien en relacion con las ramas del repositorio remoto*

    git status -b

*Para solo ver los nombres de los archivos modificados*

    git status -uno

**Formas de fusionar ramas y diferentes maneras de hacerlo**

*Fusionar rama con la rama actual*

    git merge <nombre_rama>

*Fusionar una rama en otra rama específica*

    git merge <rama_fuente> <rama_destino>

**Ahora veremos comandos para preparar los proyectos para la subida**

*Para agregar archivos especificos para el area de staging*

    git add <Nombre_del_archivo>

*Para agregar todos los archivos al area de staging*

    git add *

*Agregar una ruta especifica al area de staging*

    git add directorio/

**Formas de usar el git rm**

*Para eliminar un archivo del area de trabajo y del area de staging*

    git rm <nombre_archivo>

*Para eliminar un archivo del area de staging pero mantenerlo en el area de trabajo usaremos*

    git rm --cached <nombre_archivo>

*Para eliminar un directorio del area de staging pero mantenerlo en el area de trabajo usaremos*

    git rm -r --cached <nombre_directorio>

**Usar git mv**

*Para cambiar el nombre de un archivo usaremos*

    git mv <nombre_archivo_actual> <nuevo_nombre_archivo>

*Para mover un archivo a otro directorio*

    git mv <nombre_archivo_actual> <nueva_ruta>/<nuevo_nombre_archivo>

**Formas de usar git restore**

*Deshacer cambios en el directorio de trabajo*

    git restore <nombre_archivo>

*Deshacer cambios en el area de staging y en el area del trabajo*

    git restore --staged <nombre_archivo>

*Deshacer todos los cambios en el directorio de trabajo*

    git restore .

**Comandos para commit de los archivos en el area de staging**

*Hacer un commit con mensaje personalizado*

    git commit -m "<mensaje_commit>"

*Para editar el ultimo mensaje del commit*

    git commit --amend

*Para realizar un git add y un git commit al mismo tiempo usaremos(-a sera como git add .)*

    git commit -am "<mensaje_commit>"

## SUBIDA DE PROYECTO GIT

**Comandos push para subir los archivos a un repositorio remoto**

*Para enviar los cambios de un repositorio local a un repositorio remoto usaremos el*

    git push <nombre_repositorio_remoto> <nombre_rama>

*Para enviar los cambios de una rama local a una rama remota diferente*

    git push <nombre_repositorio_remoto> <rama_local>:<rama_remota>

*En el caso que se necesite forzar el push usaremos* **Se debe usar solo en casos especificos, se debe evitar en lo posible**

    git push --force <nombre_repositorio_remoto> <nombre_rama>




