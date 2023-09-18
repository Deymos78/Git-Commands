# CONFIGURACION DE GITLAB  

## CONFIGURACIONES INICIALES

1. Comandos para configuraciones iniciales

*Inicializaremos el repositorio local*

    git init test-project

*Podemos configurar nuestra rama principal por defecto, en este caso la llamaremos main en lugar de master(nombre por defecto)*

    git config --global init.defaultBranch main


2. Tendremos que crear una cuentade GitLab

3. Hay varias formas de conectarse a GitLab para una conexion segura se necesitara estar authenticado, esto lo podemos conseguir de las siguietnes maneras:
    
    * SSH KEY:
        
        1. Necesitaremos tener git instalado y escribir el siguiente comando en una terminal, en la de git bash se puede `ssh-keygen -t ed25519 -C "GitLab Key Pair"`, una vez ejecutado daremos enter a todo dejaremos la configuracion por defecto, esto nos generara una clave SSh con el tipo de algoritmo especificado y con el comentario de la clave especificado.

        2. Ahora accederemos al archivo desde bash con `cat ~/.ssh/<id_archivo>.pub`, copiaremos todo lo que nos ha lanzado una vez ejecutado.

        3. Por ultimo copiaremos todo lo que nos ha lanzado y lo pegaremos dentro de SSH Keys de GitLab, y haremos ninguna configuracion

        4. Para probar la conexion con el servidor de gitlab usaremos `ssh -T git@gitlab.com`, la -T sirve para que no ejecute nada mas despues de hacer la conexion.

## FLUJO DE TRABAJO DE GITLAB

**Existen 3 tipos de flujo de trabajo con git, en este caso usaremos gitlab pero las que hay incluyendo la de gitlab son:**

1. GITHUB FLOW
    
2. GIT FLOW

3. GITLAB FLOW


El flujo de trabajo de GitLab se puede resumir de la siguiente manera

* Dos variaciones
    
    * Ramas de Entorno
        * Los cambios se impulsan a través de una o más ramas de preproducción.
    
    * Ramas de lanzamiento(Release Branches) 
        * Es usado para lanzar software al mundo exterior

* Mas simple que el flujo de trabajo de Git

* Proporciona mas structura que el flujo de trabajo de GitHub


## DEMOSTRACION DE FLUJO DE TRABAJO CON GITLAB

**En este ejemplo veremos un ejemplo de sincronizar entre ramas locales y remotas en un repositorio Git, se creara MergeRequest**

1. Primero tendremos que proteger las ramas principales de esta forma se agregara una capa de seguridad a las ramas y se podra realizar merge reques despues se traeran todos los cambios de las ramas a el repositorio local

2. Despues con la rama principal local sincronizada con la remota, crearemos una nueva rama local, en la que se trabajara.

3. Se realizan los cambios necesarios y una vez finalizado se preparara la rama parar subirla al repositorio remoto para realizar una merge request y realizar el merge a la rama principal

4. En GitLab creamos el mergue request, por defecto el nombre del mergue reques sera el del commit del push, asignaremos el que solicita el Mergue Request y el que lo va a revisar.

5. Se comprobaran que los cambios esten bien y no haya fallos si se combianan en la fase de produccion, en caso de haber problemas se rechazaria y en caso de no haberlos se provaria y se realizaria el mergue correspondiente, antes de aceptar tambien se pueden colocar comentario pidiendo ajustes a los cambios realizados, se pueden editar desde el propio IDE que GitLab pone a nuestra disposicion, pero siempre se puede usar el propio IDE, realizar los cambios necesarios y realizar otro push, estos cambios se veran reflejados en el Mergue Request que sigue abierto

6. Si todo va bien entonces se realizara el Mergue Request correspondiente


