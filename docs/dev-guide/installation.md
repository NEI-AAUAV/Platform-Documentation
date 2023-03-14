## Local Installation

To run the project in your host machine, read the **Local Installation** section of each service documentation.

<!-- - [NEI Web App](../web-nei/README.md#local-installation) web_nei
- [NEI API](../api-nei/README.md#local-installation) api_nei
- [Taça UA API](../api-tacaua/README.md#local-installation) api_tacaua -->


### API NEI


### API Taça UA


### API Family



## Docker Installation

If you don't know how to install docker on Linux, we recommend you to follow this steps:

- Install Docker Engine from [Docker's apt repository](https://docs.docker.com/engine/install/ubuntu/#install-using-the-repository). Follow the 3 steps from *Set up the repository* and the 3 steps from *Install Docker Engine*.

- Afterward, follow the 4 [Linux post-installation steps](https://docs.docker.com/engine/install/linux-postinstall/#manage-docker-as-a-non-root-user) for Docker Engine to run docker without `sudo`.

- Finally, install the [Compose standalone](https://docs.docker.com/compose/install/other/#on-linux) to use `docker-compose`.\
Do not forget to run `sudo chmod +x /usr/local/bin/docker-compose` in step 2.



To run the project in docker containers, run the following commands. These will create and run the entire stack, meaning every service, in development mode. Since the containers are using bind mounts, every modification in your code will be triggered on the fly.

Creates and starts all containers of the stack. Use the flag `-d` to run in detached mode.

```
docker-compose up --build
```

Stops or starts all containers of the stack, once already created.

```
docker-compose [stop|start]
```

Stops and removes the containers, including the volumes. Use this to rebuild the stack whenever any dependency is added (e.g. a `yarn` dependency).

```
docker-compose down -v
```

To run one service individually, append the service name to the command (e.g. `api_nei`). 

```
docker-compose up --build [SERVICE...]
```

An alternative is to create the images and the container manually by reading the **Docker Installation** section in the respective service documentation.

<!-- - [NEI Web App](../web-nei/README.md#docker-installation) web_nei
- [NEI API](../api-nei/README.md#docker-installation) api_nei
- [Taça UA API](../api-tacaua/README.md#docker-installation) api_tacaua -->

### API NEI

### API Taça UA

### API Family




## Installation Troubleshooting

Common errors that can happen during installation.

### Poetry cannot install `psycopg2`

If `psycopg2` cannot be installed with `poetry install` due to the error `pg_config executable not found`, the pyscopg2 documentation recommends installing the following packages:

```
sudo apt install python3-dev libpq-dev
```

### Address already in use

If the FastAPI is having problems to start because the address is already in use, it is likely that another application is using the same port it is trying to use (the default port is **8000**). For a quick fix, kill the processes using that port with:

```
sudo fuser -k 8000/tcp
```
