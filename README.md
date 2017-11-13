# superior-prospects-composition

This repository is a composition that deploys https://github.com/shaunfowler/superior-prospects, https://github.com/shaunfowler/superior-prospects-api, and it's supporting services.

## Deployment

### Create secrets

Create two docker secrets called `sp_client_id` and `sp_client_secret`. These, respectively, represent the client ID and secreet for Google cloud APIs (https://console.cloud.google.com/apis/credentials).

### Deploy the stack

To deploy the stack in swarm, run:

```
docker swarm init
docker stack deploy -c docker-compose.yml superior_prospects
```

#### Mock data

To seed mongo with mock data, run:

```
docker stack deploy -c docker-compose.seed.yml superior_prospects
```