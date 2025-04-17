# 🗂️ MinIO - Almacenamiento de Objetos

MinIO es un servicio de almacenamiento de objetos compatible con S3. Este repositorio contiene los archivos necesarios para desplegar MinIO utilizando Docker Compose.

## 🚀 Cómo Configurar el Servicio

1. 📄 **Copia el archivo `example.env` a `.env`**  
   ```bash
   cp example.env .env
   ```
   Configura las variables de entorno en el archivo `.env` según tus necesidades:
   - `MINIO_ROOT_USER`: Usuario administrador de MinIO.
   - `MINIO_ROOT_PASSWORD`: Contraseña del usuario administrador.
   - `MINIO_DOMAIN`: Dominio para acceder al servicio.

2. 📂 **Configura los volúmenes**  
   Asegúrate de que el directorio `/home/bryan/minio/data` exista en tu sistema. Este será el lugar donde se almacenarán los datos.

3. ✏️ **Revisa el archivo `docker-compose.yml`**  
   Verifica que las configuraciones sean correctas, como los puertos y el usuario que ejecutará el contenedor.

## 🐳 Cómo Ejecutar el Servicio

1. **Levanta el servicio con Docker Compose**  
   ```bash
   docker compose up -d
   ```
   Esto iniciará el contenedor de MinIO en segundo plano.

2. **Accede al panel de administración**  
   - URL del panel: `http://<tu-dominio>:9001`
   - Credenciales: Usa el usuario y contraseña configurados en el archivo `.env`.

## 📚 Notas Adicionales

- Asegúrate de que la red `proxy` exista antes de ejecutar el contenedor. Puedes crearla con:
  ```bash
  docker network create proxy
  ```
- Para detener el servicio, usa:
  ```bash
  docker compose down
  ```

¡Listo! 🎉 Ahora puedes usar MinIO como tu solución de almacenamiento de objetos.
