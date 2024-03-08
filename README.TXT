- Cada imagen docker tiene que tener un dockerfile indicando como se organiza.
- De una imagen docker puedo sacar muchos containers, mientras lo permita la memoria.
- El jenkins persiste datos. Cuando se para hay que guardar los datos en el disco duro, porque si no se pierden.
- Cuando se destruye el container, todo lo que se haya creado, se borra.
- Para construir la imagen: docker compose build []

COMANDOS:

- docker compose build
- docker compose ps 
- docker images
- docker compose up -d [sistema] #-d significa detach
- docker rm -f [id] #cargate el contenedor con el id [id]
- docker exec -it knowmadmood-jenkins bash

NOTAS:

SRP - principio de mínima responsabilidad. (cada tarea de jenkins debe ser, a ser posible, SRP)
Facade Pattern - La tarea principal se comporta como un intercambiador. Se encarga de esperara a que las tareas hijas terminen y llama a otro proceso.
Los ficheros que se generan están en /var/lib/docker (dónde está ese dir?)

// para migrar
te copias los volumenes de los directorios /var/lib/docker/volumes 
y en la otra máquina le dices docker volume create [nombre carpeta]
y luego copias los contenidos de las carpetas que te copiaste en el de la carpeta nueva

### con respecto a jenkins
plugin util:
- Dia2: plugin de roles: busca "role" y el que sale. Este sirve para que cada rol solo vea unos trabajos y no otros
- Dia3: jenkins versión master-slave:
    en el jenkins maestro te tienes que hacer una credencial (user y pass: minion1 // minion2 dependiendo del minion al que te loguees. los administradores de los minions son "minion1" y "minion2" respectivamente)
    en el apartado de nodos:
        la etiqueta designa el minion que se va a usar, es super importante.
        remote root directory: /var/jenkins_home/minion1
        labels: minion1
        conexión por via ssh:
            nombre de la máquina: [LO DEJAMOS POR IMPOSIBLE HASTA EL LUNES]
Pipeline syntax:
https://www.jenkins.io/doc/book/pipeline/syntax/

Job de tipo pipeline: 
en una pipeline -> Pipeline -> steps -> sample step: nos sirve para ver ejemplos.

