# Preguntale al Candidato - Database

Este repositorio contiene la infrastructura necesaria para desplegar la base de datos [Milvus](https://milvus.io).

## Despliegue local

Dentro de la carpeta local (`cd local`), podrá encontrar un ejemplo sobre como ejecutar Milvus localmente utilizando Docker Compose.

Utilice los comandos definidos en el Makefile para mayor simplicidad.

- `make start`: para lanzar la ejecuón de la base de datos.
- `make logs container=milvus-standalone`: para ver los logs de la base de datos.
- `make connect`: para ver la IP y el puerto que se necesita para conectarse a la base de datos.
- `make clean`: para detener la base de datos y limpiar los archivos.
