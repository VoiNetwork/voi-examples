# Voi Examples

This repository contains examples that can be used to help build mental models on how use/integrate 
with the Voi network.

## Indexer

This project contains a Docker compose file and configurations for running an indexer on the network.

The Docker Compose file defines the following servers:

1. **voinode**: This service runs the node that connects to the Voi network.
2. **conduit**: This service runs the Conduit service that fetches data from **voinode** and stores data in a Postgres db.
2. **postgres**: This service runs the Postgres db that stores the data processed by the Conduit service. Data is stored on a Docker volume.
2. **indexer**: This service runs the indexer that fetches data from the Postgres db.

### Running the project

```sh
docker compose up -d
```

### Stopping the project

```sh
docker compose down
```

### Connecting to the indexer

```sh
curl http://localhost:8980/v2/accounts
```

### Conduit configuration

Documentation on the conduit configuration can be found [here](https://github.com/algorand/conduit?tab=readme-ov-file#create-conduityml-configuration-file)

### Indexer configuration

Documentation on the indexer configuration can be found [here](https://github.com/algorand/indexer?tab=readme-ov-file#disabling-parameters)

### Indexer REST API documentation

The indexer REST API documentation can be found [here](https://developer.algorand.org/docs/rest-apis/indexer/)