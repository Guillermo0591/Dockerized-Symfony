# Dockerized Symfony 

## Docker Setup
```
docker-compose up -d --build
```
Si todo ha ido bien, deberías obtener una salida similar a la siguiente:
```
symfony-docker_nginx_1 is up-to-date
symfony-docker_php_1 is up-to-date
Creating symfony-docker_mysql_1 ... done
```

## Instalación Symfony
Puesto que a partir de ahora trabajaremos con nuestros 
contenedores, la instalación de Symfony la realizaremos 
dentro de ellos y no desde nuestro sistema operativo.

Por tanto, lo primero que tendremos que hacer es acceder 
a nuestro contenedor donde se encuentra 
PHP (acordaos de haberlo levantado) mediante el comando:
```
docker exec -it  symfony-docker_php_1 bash
```
Donde **symfony-docker_php_1** es el nombre que os haya 
devuelto el comando docker-compose up tras haber terminado 
de lanzar los contenedores.

Ahora ya dentro del container podremos instalar Symfony tal 
y como sugiere la documentación:
```
curl -sS https://get.symfony.com/cli/installer | bash
mv /root/.symfony/bin/symfony /usr/local/bin/symfony
symfony new symfony --dir=/var/www/symfony
```

## Notas
Puede que la creación del proyecto puede dar el siguiente fallo:
```
*** Please tell me who you are.
Run
git config --global user.email "you@example.com"
git config --global user.name "Your Name"
to set your account's default identity.
```
Con realizar la configuración de Git que solicita se resolverá sin mayor complicación.
