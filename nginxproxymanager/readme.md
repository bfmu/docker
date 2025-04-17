# 🌐 Nginx Proxy Manager

Nginx Proxy Manager es una herramienta fácil de usar para gestionar proxies inversos con soporte para certificados SSL.

## 🚀 Cómo Configurar y Ejecutar el Servicio

1. 📂 **Crea la red necesaria**  
   Antes de iniciar el servicio, asegúrate de crear la red `proxy` que será utilizada por este y otros servicios:
   ```bash
   docker network create proxy
   ```

2. 🐳 **Levanta el servicio con Docker Compose**  
   Ejecuta el siguiente comando para iniciar Nginx Proxy Manager:
   ```bash
   docker compose up -d
   ```

3. 🌐 **Accede a la interfaz de administración**  
   - URL: `http://<tu-dominio>:81`
   - Credenciales predeterminadas:
     - Usuario: `admin@example.com`
     - Contraseña: `changeme`

4. 🔗 **Agrega otros servicios a la red `proxy`**  
   Para que otros servicios sean accesibles a través de Nginx Proxy Manager, asegúrate de que estén conectados a la red `proxy`. Por ejemplo, en el archivo `docker-compose.yml` de cada servicio, agrega:
   ```yaml
   networks:
     proxy:
       external: true
   ```

5. ⚙️ **Configura los proxies desde la interfaz**  
   Una vez dentro de la interfaz de administración, puedes agregar hosts, configurar certificados SSL y gestionar tus proxies.

## 📚 Notas Adicionales

- Para detener el servicio, usa:
  ```bash
  docker compose down
  ```
- Asegúrate de que los volúmenes `data` y `letsencrypt` estén correctamente configurados para persistir la información.

¡Listo! 🎉 Ahora puedes gestionar tus proxies de manera sencilla con Nginx Proxy Manager.
