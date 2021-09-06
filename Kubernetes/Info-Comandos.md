# **KUBERNETES**

# Principales componentes

1. **PODS**: Unidad mas pequeña que se puede desplegar y gestionar en kubernetes. Es un grupo de uno o mas contenedores que comparten almacenamiento, red y especificaciones de como ejecutarse. Son efimeros.

2. **Deployments**: Describe el estado deseado de una implementacion, ejecuta multiples replicas de la aplicacion, reemplaza las que se encuentre defectuosas o las que no responden.

3. **Services**: Definicion de como exponer una aplicacion que se ejecuta en un conjunto de pods como un servicio de red (por defecto se usa roud-robin para balanceo de carga).

4. **Config Map**: Permite desacoplar la configuracion para hacer las imagenes mas portables, almacenan variables de entorno, argumentos para linea de comandos, o configuracion de volumenes que puedan consumir los pods.

5. **Labels**: Pares de clave valor *("enviroment" : "qa")* para organizar, seleccionar, consultar y monitorear objetos de forma mas eficiente, ideales para UI y CLIs.

6. **Selectores**: Mecanismo para hacer consultas a las etiquetas. *kubectl get pods -l 'enviroment in (production), tier in (frontend)*.

# **ARQUITECTURA**

Cuando se implementa kubernetes se obtiene un cluster. Un cluster de kubernetes consta de un conjunto de maquinas trabajadoras, llamadas nodos, que ejecutan aplicaciones en contenedores. Cada cluster tiene al menos un nodo trabajador. Los nodos trabajadores alojan a los pods que son los componentes de la carga de trabajo de la aplicacion.

* **kube-apiserver**: Proveela interaccion para herramientas de administracion kubectl or Kubernetes dashboard.
* **etcd**: Almacenamiento, mantine la configuracion y el estado del cluster.
* **kube-scheduler**: Al crear o escalar las aplicacionesselecciona el nodo para los pods y los ejecuta.
* **kube-controller-manager** Supervisa controladores mas pequeños que ejecutan tareas de replicar pods y manejar operaciones de los nodos.

# **INSTALACION**

## MINICUBE y KUBECTL

- Los pasos para la instalacion se encuentran en el siguiente enlace: https://v1-18.docs.kubernetes.io/docs/tasks/tools/install-minikube/


## Aspectos importantes.

### Driver

Hace referencia al hipervisor con el cual se va a trabajar para la orquestacion de nodos:

- Hyper-V
- Contenedores con Docker
- VirtualBox


### Comandos minikube

* **minikube status** Para visualizar el estado actual 
* **minikube stop** Parar minikube
* **minikube start** Iniciar minikube
* **minikube dashboard** Obtener url web de minikube

### Comandos principales

#### Crear POD (Partiendo de una imagen en dockerhub)

* **kubectl run kbillingapp --image=sotobotero/udemy-devops:0.0.1 --port=80 80** --> kubectl run (nombre POD) --image=IMAGEN --port : puerto.
* **kubectl get pods**: Obtener todos los PODS creados.
* **kubectl describe pod (NombrePOD)**: Informacion del POD.
* **kubectl expose pod kbillingapp --type=LoadBalancer --port 8080 --target-port=80**: Crear el servicio exponiendo el POD
* **kubectl get services**: Obtener todos los servicios creados.
* **kubectl describe service (NombreService)**: Informacion del Servicio.
* **minikube service (nombre servicio)kbillingapp**: Obtener informacion para acceso al service. 

#### Crear objetos en el cluster

* **kubectl apply -f (nombre del archivo)**: Crear objetos a partir de los arhcivos yaml
* **kubectl get all**: Obtener informacion general del dashboard