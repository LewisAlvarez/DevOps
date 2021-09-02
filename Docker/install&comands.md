# Instalacion Docker

## **Docker Engine para Ubuntu**

##### La documentacion para la instalacion de docker engine se encuentra en el siguiente enlace:

* https://docs.docker.com/engine/install/ubuntu/


##### La documentacion para la instalacion de docker engine se encuentra en el siguiente enlace:

* https://github.com/docker/compose/releases/

### Para usar comandos de docker sin anteponer "sudo": **sudo usermod -aG docker ${USER}**

## **Comandos principales**

- **Listar Imagenes:** *docker image ls*
- **Listar Contenedores:** *docker ps -a*
- **Inicializar contenedor** *docker start (Nombre/IdContenedor)*
- **Visualizar los Logs** *docker logs (Nombre/IdContenedor)*
- **Parar un contenedor** *docker stop (Nombre/IdContenedor)*
- **Eliminar un contenedor** *docker rm (Nombre/IdContenedor)*
- **Eliminar una imagen** *docker rmi (Nombre/IdImagen)*
- **Correr un contenedor (Para este ejemplo)** *docker run -p 80:80 -p  8080:8080 --name billingapp sotobotero/udemy-devops:0.0.1*
- **Eliminar todos los contenedores** *docker system prune*
- **Eliminar todas las imagenes** *docker system prune*
- **Eliminar todos los volumenes** *docker image prune*
- **Ver estadisticas de uso de recursos** *docker stats*

## **Docker Compose**

- **Ejecutar docker-compose para bajar imagenes del docker hub:** *docker-compose pull* Cuando el archivo .yml se llama docker-compose.yml
- **Ejecutar docker-compose para construir imagenes** *docker-compose build* Cuando el archivo .yml se llama docker-compose.yml
- **Ejecutar docker-compose:** *docker-compose -f (nombre.yml) pull* Cuando el archivo .yml **NO** se llama docker-compose.yml
- **Parar docker-compose:** *docker-compose -f (nombre.yml) stop* Cuando el archivo .yml **NO** se llama docker-compose.yml
- **Crear contenedores** *docker-compose up -d* Cuando el archivo .yml se llama docker-compose.yml (-d para que no se quede el primer plano)
- **Crear contenedores** *docker-compose -f (nombre.yml) up -d* Cuando el archivo .yml se llama docker-compose.yml 
- **Parar y Eliminar contenedores** *docker-compose down* Para y elimina los contenedores que se encuentren en el docker-compose file

- **Escalar** *docker-compose -f (nombre.yml) up --scale nombreImagen=CantidadContenedores(Numero) -d --force-recreate* 

- **Crear imagen:** *docker build -t billingapp:prod --no-cache --build-arg JAR_FILE=target/*.jar .* (Caso de ejemplo)


