# Documentacion para crear Jobs, Pipelines en Jenkins

## Pasos

1. Create a job
2. Opciones: Crear un proyecto de estilo libre o Pipelines
3. Configurar el origen del codigo fuente: Seleccionar Git e ingresar la URL del repositorio objetivo.
4. Configuracion del pom.xml


# Jenkins con Github
## WebHooks

Permite tener comunicacion basada en eventos, desde el repositorio de codigo a otros programas interesados, Ej: Jenkins.
Para hacer uso de webhooks nuestro servidor de integracion continua tiene que ser visible desde internet.

La ruta es la siguiente para la configuracion en GitHub:

1. Dentro del repositorio ir a la opcion de configuracion o settings.
2. Dirigirse a la opcion webhooks.
3. En el campo Payload URL, poner la direccion del servidor de integracion continua Jenkins.
4. En el campo Content Type escoger la opcion: application/json.

![Pasos1a4ConfiguracionWebhook](./images/pasos1a4.png)

5. Escoger por cuales eventos se desea recibir notificaciones a jenkins (Solo por eventos push, cualquier evento o de manera personalizada).

![Pasos5webhook](./images/paso5.png)

