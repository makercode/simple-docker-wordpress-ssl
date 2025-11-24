# Simple docker wordpress SSL

Repositorio Original: https://github.com/wazooinc/local-wordpress-development/tree/main

Puntos a tener en cuenta:
- El docker utiliza __mkcerts__ para las llaves autofirmadas y hay que instalarlo para usarlo. Instalación y documentación: (https://github.com/FiloSottile/mkcert)
- Se tienen que seguir instrucciones antes de correr el docker

## Pasos para linux debian:
1. Descargar el zip o "git clone git@github.com:makercode/simple-docker-wordpress-ssl.git"
2. Instalar con las instrucciones mkcerts e instalar los certificados
  - Crear alias "127.0.0.1 __example.com__" en /etc/hosts
  - "mkcert -install" en la carpeta base de proyecto
  - "mkcert __example.com__" dentro de carpeta "/nginx/certs"
  - Asegurarse que en "nginx/default.conf" el alia corresponda para que el shell dentro de docker los copie y use:
    - ssl_certificate /etc/nginx/certs/__example.com__.pem; 
    - ssl_certificate_key /etc/nginx/certs/__example.com__-key.pem;
3. Copiar y cambiar variables de entorno en "example.env" a ".env"
  - CONTAINER_NAME es solo un prefijo aleatorio para los nombres
5. correr los contenedores docker con "docker compose up" o "docker compose up -d"
