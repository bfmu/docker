# OpenProject con Docker Compose

Este proyecto configura y ejecuta una instancia de [OpenProject](https://www.openproject.org/) utilizando Docker Compose. OpenProject es una solución de gestión de proyectos de código abierto que permite la planificación, seguimiento y colaboración en proyectos.

## Requisitos previos

Antes de comenzar, asegúrate de tener instalados los siguientes componentes en tu sistema:

- [Docker](https://www.docker.com/)
- [Docker Compose](https://docs.docker.com/compose/)

## Configuración

El archivo `docker-compose.yml` incluido en este repositorio define los servicios necesarios para ejecutar OpenProject. A continuación, se describen los pasos para configurarlo:

1. **Clonar el repositorio**  
   Clona este repositorio en tu máquina local:
   ```bash
   git clone <URL_DEL_REPOSITORIO>
   cd openproject
   ```

2. **Configurar volúmenes**  
   Asegúrate de que las carpetas `pgdata` y `assets` existan en el directorio raíz del proyecto. Estas carpetas se utilizan para persistir los datos de la base de datos y los archivos de OpenProject.

   Si no existen, puedes crearlas con:
   ```bash
   mkdir pgdata assets
   ```

3. **Configurar red externa**  
   Este proyecto utiliza una red externa llamada `proxy`. Asegúrate de que la red exista ejecutando:
   ```bash
   docker network create proxy
   ```

## Ejecución

Para iniciar el servicio, ejecuta el siguiente comando en el directorio raíz del proyecto:

```bash
docker-compose up -d
```

Esto descargará la imagen de OpenProject, creará los contenedores y los iniciará en segundo plano.

## Acceso a OpenProject

Una vez que el servicio esté en ejecución, puedes acceder a OpenProject desde tu navegador en la siguiente URL:

- **URL:** [http://trello.bfmu.dev](http://trello.bfmu.dev)

## Variables de entorno

El archivo `docker-compose.yml` incluye las siguientes variables de entorno que puedes personalizar según tus necesidades:

- `OPENPROJECT_SECRET_KEY_BASE`: Clave secreta para la aplicación.
- `OPENPROJECT_HOST__NAME`: Nombre del host donde se ejecutará OpenProject.
- `OPENPROJECT_HTTPS`: Define si se utiliza HTTPS (por defecto `false`).
- `OPENPROJECT_DEFAULT__LANGUAGE`: Idioma predeterminado de la aplicación (por defecto `es`).

## Detener el servicio

Para detener el servicio, ejecuta:

```bash
docker-compose down
```

Esto detendrá y eliminará los contenedores, pero los datos persistirán en los volúmenes configurados.

## Notas adicionales

- Asegúrate de que el puerto 80 no esté en uso por otros servicios en tu máquina.
- Si necesitas exponer el servicio en un puerto diferente, descomenta y ajusta la sección `ports` en el archivo `docker-compose.yml`.

Para más información sobre OpenProject, visita su [documentación oficial](https://www.openproject.org/docs/).

