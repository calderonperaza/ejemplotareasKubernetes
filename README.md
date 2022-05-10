# Ejemplo Tareas Kubernetes!

El siguiente repositorio contiene los archivos para desplegar una aplicación de ejemplo en **kubernetes** empleando minikube.


## Proyectos empleados:

En el ejemplo tareas, se tienen tres elementos: la base de datos, el backend y el frontend. La base de datos se levanta en el yamel denominado 1basededatos.yml, y emplea un volumen persistente.

### Backend

Es un proyecto en Node JS, una api rest que conecta a una base de datos NO SQL de mongoDB, el fuente del proyecto se encuentra en el siguiente enlace:
[Proyecto Backend NodeJS-Express-Mongodb](https://github.com/calderonperaza/ejemplotareasBackEndExpress)
Dentro del proyecto encontrará el respectivo DockerFile con la definición del contenedor que luego para poderse desplegar se encuentra publicado en docker hub:
[DockerImagen-Ejemplo-Tarea-Backend](https://hub.docker.com/repository/docker/calderonperaza/ejemplobackend)

### FrontEnd

Es un proyecto en Vue 2, emplea vuetify y consume la api rest del backend, este proyecto lo encuentra en el siguiente enlace:
[ejemploTareasFrontEnd](https://github.com/calderonperaza/ejemplotareasfrontend)
Dentro del proyecto encontrará el respectivo DockerFile con la definición del contenedor que luego para poderse desplegar se encuentra publicado en docker hub:
[imagenEjemploTareasFrontEnd](https://hub.docker.com/repository/docker/calderonperaza/ejemplofrontend)
el backend se refiere colocando la ip del cluster y el puerto expuesto por el servicio backend
por ejemplo:
axios.defaults.baseURL="http://192.178.103.15:30000"

## Importante

Para exponer la apps se utiliza un **ingress** por lo que debe habilitar dicho addons en el minikube.
