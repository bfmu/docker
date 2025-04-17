# 🚀 Servicios con Docker Compose

Este repositorio recopila configuraciones de `docker-compose` para ejecutar aplicaciones de manera fácil y centralizada. Cada directorio contiene la configuración básica y una explicación detallada de cómo desplegar el servicio correspondiente.

## 🏗️ Arquitectura general

### 1️⃣ Proxy reverso con Nginx  
El primer paso para utilizar este repositorio es levantar el servicio de Nginx, que actúa como proxy reverso. Este proxy permite acceder a los servicios a través de un DNS personalizado. Para ello, todos los servicios que desees exponer deben unirse a la red externa llamada `proxy`.

### 2️⃣ Portainer (opcional)  
Portainer es un servicio opcional pero altamente funcional para gestionar contenedores y Docker en general. Puedes utilizarlo para monitorear, administrar y desplegar contenedores de manera gráfica.

## 📋 Menú de servicios

A continuación, se presenta un menú interactivo con los servicios disponibles en este repositorio. Cada servicio tiene su propio directorio con la configuración necesaria y una guía para desplegarlo.

- 🌐 [**Nginx Proxy Manager**](./nginxproxymanager): Configuración del proxy reverso basado en Nginx.
- 🗂️ [**Portainer**](./portainer): Herramienta gráfica para gestionar contenedores (opcional).
- 📊 [**OpenProject**](./openproject): Solución de gestión de proyectos de código abierto.
- ☁️ [**Nextcloud AIO**](./nextcloud-aio): Plataforma de almacenamiento y colaboración en la nube.
- 🗃️ [**MinIO**](./minio): Almacenamiento de objetos compatible con S3.
- 🔍 [**Elasticsearch y Kibana**](./elasticsearch): Motor de búsqueda y visualización de datos.
- 🤖 [**IA (ChatGPT y Ollama)**](./IA): Servicios de inteligencia artificial y modelos de lenguaje.

## 🛠️ Cómo empezar

1. **Levantar el proxy reverso**  
   Dirígete al directorio `nginxproxymanager` y sigue las instrucciones para desplegar el servicio de Nginx. Esto configurará el proxy reverso y la red `proxy`.

2. **Desplegar servicios adicionales**  
   Cada servicio adicional debe unirse a la red `proxy` para ser accesible a través del DNS configurado. Consulta las instrucciones específicas en el directorio correspondiente.

3. **(Opcional) Desplegar Portainer**  
   Si deseas gestionar tus contenedores de manera gráfica, despliega Portainer siguiendo las instrucciones en su directorio.

## 📚 Notas adicionales

- Asegúrate de que Docker y Docker Compose estén instalados en tu sistema antes de comenzar.
- Personaliza las configuraciones según tus necesidades, como nombres de host, puertos y variables de entorno.

¡Explora los servicios y simplifica la gestión de tus aplicaciones con Docker Compose! 🎉
