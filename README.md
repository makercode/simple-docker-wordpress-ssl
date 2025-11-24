# Simple docker wordpress SSL

Repositorio Original: https://github.com/wazooinc/local-wordpress-development/tree/main

Puntos a tener en cuenta:
- El docker utiliza mkcerts para las llaves autofirmadas. (https://github.com/FiloSottile/mkcert)
- Se tienen que seguir instrucciones antes de correr el docker

## Pasos para linux debian:
1. Descargar el zip o "git clone git@github.com:makercode/simple-docker-wordpress-ssl.git"
2. Instalar con las instrucciones mkcerts e instalar los certificados
  - Crear alias "127.0.0.1 example.com" en /etc/hosts
  - "mkcert -install" en la carpeta base de proyecto
  - "mkcert example.com" dentro de carpeta "/nginx/certs" 
3. Copiar y cambiar variables de entorno en "example.env" a ".env"
4. Agregar en .env la variable HOSTNAME con "example.com"
5. correr docker compose up
