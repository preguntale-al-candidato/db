# Preguntale al Candidato - Database

## Qdrant

Qdrant is a vector similarity search engine that provides a production-ready service with a convenient API to store, search, and manage points (i.e. vectors) with an additional payload.

### Distributed deployment

Based on the [documentation](https://qdrant.tech/documentation/guides/distributed_deployment/) in the `local` folder there is an example using docker-compose to deploy it in a distributed way with three nodes.

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
