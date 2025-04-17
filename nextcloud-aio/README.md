# 🌐 Nextcloud All-in-One (AIO)

Este repositorio contiene los archivos necesarios para desplegar Nextcloud AIO utilizando Docker Compose.

## 🚀 Cómo Configurar y Ejecutar el Servicio

1. 📄 **Copia el archivo `example.env` a `.env`**  
   ```bash
   cp example.env .env
   ```
   Configura las variables de entorno en el archivo `.env` según tus necesidades:
   - `APACHE_PORT`: Puerto en el que se ejecutará Apache.
   - `APACHE_IP_BINDING`: Dirección IP de enlace para Apache.
   - `NEXTCLOUD_DATADIR`: Directorio donde se almacenarán los datos de Nextcloud.
   - `NEXTCLOUD_MAX_TIME`: Tiempo máximo de ejecución para procesos largos.
   - `NEXTCLOUD_MEMORY_LIMIT`: Límite de memoria para Nextcloud.

2. 🐳 **Levanta el servicio con Docker Compose**  
   ```bash
   docker compose up -d
   ```
   Esto iniciará el contenedor de Nextcloud AIO en segundo plano.

3. 🔑 **Obtén la contraseña de administración**  
   Ejecuta el siguiente comando para obtener la contraseña de Nextcloud AIO:
   ```bash
   sudo cat /var/lib/docker/volumes/nextcloud_aio_mastercontainer/_data/data/configuration.json | grep password
   ```

4. 🌐 **Accede a la interfaz de Nextcloud AIO**  
   - URL: `http://<tu-dominio>:8080`
   - Usa la contraseña obtenida en el paso anterior.

## ⚠️ Posibles Errores y Soluciones

### 🛠️ **Caddy warning: failed to sufficiently increase receive buffer size**
- **Causa:** El tamaño del buffer de recepción es insuficiente.
- **Solución Permanente:**  
  Ejecuta el siguiente comando para configurar el tamaño del buffer y aplicarlo tras reiniciar:
  ```bash
  echo "net.core.rmem_max = 2500000" | sudo tee /etc/sysctl.d/nextcloud-aio-buffer-increase.conf
  ```
  Reinicia el sistema para aplicar los cambios.

- **Solución Temporal:**  
  Ejecuta este comando para aplicar el cambio sin reiniciar:
  ```bash
  sudo sysctl net.core.rmem_max=2500000
  ```
  Luego, reinicia Nextcloud AIO desde la interfaz de administración.

## 📚 Notas Adicionales

- Para detener el servicio, usa:
  ```bash
  docker compose down
  ```
- Asegúrate de que los volúmenes y configuraciones sean correctos antes de iniciar el servicio.

¡Listo! 🎉 Ahora puedes disfrutar de tu instancia de Nextcloud AIO.

