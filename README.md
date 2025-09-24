🚀 Guía: Servir tu página con Nginx en Docker
📥 1. Descargar Nginx en Docker

Primero, descarga la imagen oficial de Nginx y crea un contenedor:

docker pull nginx
docker run --name mi-nginx -p 8080:80 -d nginx


👉 Ahora abre en tu navegador:
http://localhost:8080

Y verás la página de bienvenida de Nginx.

📂 2. Acceder al directorio de Nginx dentro del contenedor

Accede al contenedor y muévete al directorio donde se sirven los archivos:

docker exec -it mi-nginx bash
cd /usr/share/nginx/html
ls


👉 Aquí están los archivos que sirven tu web (index.html, etc).

🍴 3. Hacer un fork y clonar tu proyecto de GitHub

En tu PC descarga tu proyecto:

git clone https://github.com/tu-usuario/tu-repo.git


👉 Esto creará la carpeta tu-repo con tus archivos.
Por ejemplo, si tu archivo principal es ventaentradas.html, estará dentro de esa carpeta.

📌 Alternativa:
También puedes descargar el proyecto como ZIP, descomprimirlo y luego copiar los archivos necesarios.

📤 4. Copiar tu página al contenedor

En Windows (cambia la ruta por la tuya):

docker cp "C:\Users\TuUsuario\Documents\tu-repo\ventaentradas.html" mi-nginx:/usr/share/nginx/html/


👉 Esto mete tu archivo en el directorio de Nginx dentro del contenedor.

✏️ 5. Renombrar tu archivo como index.html

Entra otra vez al contenedor y cambia el nombre del archivo:

docker exec -it mi-nginx bash
cd /usr/share/nginx/html
mv ventaentradas.html index.html


👉 Ahora abre de nuevo:
http://localhost:8080

Y ya verás tu página como la principal 🎉.
