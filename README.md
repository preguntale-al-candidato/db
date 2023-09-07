# Preguntale al Candidato - Database

## Milvus

This repository will contain the require infrastructure to deploy Milvus locally and in a distributed way as indicated in the [documentation](https://milvus.io/docs).

### Local deployment

The `local` folder contains an example using `docker-compose`` to deploy the database locally.

Use the commands from Makefile to interact with the deployment.
```
cd local
make start
make logs container=milvus-standalone
make connect
make clean
```
