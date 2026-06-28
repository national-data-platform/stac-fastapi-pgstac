
This repo is contains the services for running STAC on NDP.

Two full stacks are run for STAC and PRESTAC. The same docker compose file
is used for both, and the configuration differences are in the env files.
When running `docker compose`, you must use `-p xxxx`: this specifies
the prefix of the container names so that stac and prestac services have
unique container names.


To start stac and prestac:
```
docker compose -p stac --env-file .env.stac up -d
docker compose -p prestac --env-file .env.prestac up -d
```

To stop stac and prestac:
```
docker compose -p stac --env-file .env.stac down
docker compose -p prestac --env-file .env.prestac down
```

To restart if the compose or env file changes:
```
docker compose -p stac --env-file .env.stac up -d --no-deps
docker compose -p prestac --env-file .env.prestac up -d --no-deps
```
