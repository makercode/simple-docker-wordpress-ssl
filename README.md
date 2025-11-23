
Repositorio Original: https://github.com/FiloSottile/mkcert

Puntos a tener en cuenta:
1. El docker utiliza mkcerts para las llaves autofirmadas. (https://github.com/FiloSottile/mkcert)
2. Se tienen que seguir instrucciones antes de correr el docker

Pasos para linux debian:
- Descargar el zip o "git clone git@github.com:makercode/simple-docker-wordpress-ssl.git"
- Instalar con las instrucciones mkcerts e instalar los certificados
  - Crear alias "127.0.0.1 example.com" en /etc/hosts
  - "mkcert -install" en la carpeta base de proyecto
  - "mkcert example.com" dentro de certs 
- Copiar y cambiar variables de entorno en "example.env" a ".env"
- Agregar en .env la variable HOSTNAME con "example.com"
- correr docker compose up
