# Preguntale al Candidato - Database

## Qdrant

Qdrant is a vector similarity search engine that provides a production-ready service with a convenient API to store, search, and manage points (i.e. vectors) with an additional payload.

This repository will contain the require infrastructure to deploy Qdrant in a distributed way as indicated in the [documentation](https://qdrant.tech/documentation/guides/distributed_deployment/).

### Local deployment

The `local` folder contains an example using docker-compose to deploy it Qdrant with three nodes.

To run the database execute the following commands:
```
cd local
docker-compose up --detach
```

To check the logs for each of the nodes run:
```
docker logs local-qdrant_node_1-1
docker logs local-qdrant_node_2-1
docker logs local-qdrant_node_3-1
```

To stop the cluster run:
```
docker-compose down
```
