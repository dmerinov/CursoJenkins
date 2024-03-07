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