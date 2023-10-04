# Preguntale al Candidato - Base de datos

Este repositorio contiene la infraestructura necesaria para desplegar la base de datos [Milvus](https://milvus.io).

## Despliegue local

Dentro de la carpeta local (`cd local`), podrá encontrar un ejemplo sobre como ejecutar Milvus localmente utilizando Docker Compose.

Utilice los siguientes comandos para correr una instancia local de la base de datos definidos en el Makefile para mayor simplicidad.

1. Obtener un backup desde S3. Omitir si se desea correr una instancia limpia.

```bash
aws s3 sync s3://milvus-volume volumes
```

2. Ejecute el servidor

```bash
docker-compose --project-name pac --file docker-compose.yml up --detach
```

3. Confirme que el servicio esta corriendo

```bash
docker-compose --project-name pac --file docker-compose.yml ps
```

El resultado debería ser:

```
PS D:\Julian\Code\preguntale-al-candidato\db\local> docker-compose --project-name pac --file docker-compose.yml ps
      Name                     Command                  State                                           Ports
--------------------------------------------------------------------------------------------------------------------------------------------------
milvus-etcd         etcd -advertise-client-url ...   Up (healthy)   2379/tcp, 2380/tcp
milvus-minio        /usr/bin/docker-entrypoint ...   Up (healthy)   0.0.0.0:9000->9000/tcp,:::9000->9000/tcp,
                                                                    0.0.0.0:9001->9001/tcp,:::9001->9001/tcp
milvus-standalone   /tini -- milvus run standalone   Up (healthy)   0.0.0.0:19530->19530/tcp,:::19530->19530/tcp,
                                                                    0.0.0.0:9091->9091/tcp,:::9091->9091/tcp
PS D:\Julian\Code\preguntale-al-candidato\db\local>
```

4. Correr el backend

Una vez que la base de datos esta lista, a partir del repositorio [preguntale-al-candidato/backend](https://github.com/preguntale-al-candidato/backend) podrá correr la API y realizar la ingestion de datos.
