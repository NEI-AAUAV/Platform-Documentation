# Installation


## Docker Installation

This is a walkthrough on how to run each service in **docker containers**.<br>
You can use `docker-compose` to install and run every service or a single service easily.<br>
On alternative, you can use `docker` to create the images and the container manually by following the respective service section below.

If you don't know how to install docker on Linux, we recommend you to follow this steps:

- Install Docker Engine from [Docker's apt repository](https://docs.docker.com/engine/install/ubuntu/#install-using-the-repository). Follow the 3 steps from *Set up the repository* and the 3 steps from *Install Docker Engine*.

- Afterward, follow the 4 [Linux post-installation steps](https://docs.docker.com/engine/install/linux-postinstall/#manage-docker-as-a-non-root-user) for Docker Engine to run docker without `sudo`.

- Finally, install the [Compose standalone](https://docs.docker.com/compose/install/other/#on-linux) to use `docker-compose`.<br>
**NOTES:** You may need to run `curl` with `sudo`, and do not forget to run `sudo chmod +x /usr/local/bin/docker-compose` in step 2.


### Platform (run everything)

These commands will use `docker-compose` to create and run the entire stack, meaning every service, in development mode. Since the containers are using bind mounts, every modification in your code will be triggered on the fly and update the containers.

If you want to create the images and the container manually 

Create and start all containers of the stack. Use the flag `-d` to run in detached mode.
```
docker-compose up --build
```

Stop or start all containers of the stack, once already created.
```
docker-compose [stop|start]
```

Stop and remove the containers, including the volumes. Use this to rebuild the stack whenever any dependency is added (e.g. a `yarn` dependency).
```
docker-compose down -v
```

To run one service individually, append the service name to the command (e.g. `api_nei`). 
```
docker-compose up --build [SERVICE...]
```


### Services (run individually)

<details>
<summary>Web-App NEI (web-nei)</summary>
<br>

*To be written...*
</details>


<details>
<summary>API NEI (api-nei)</summary>
<br>

Create the container for two PostgreSQL databases, postgres and postgres_test.
```
docker run -d -p 0.0.0.0:5432:5432 -e POSTGRES_DB="postgres_test" -e POSTGRES_PASSWORD="postgres" --name pg_db postgres:15-alpine
```
On the service's root directory `/api-nei`, build the image that will be used to create the service container. The flag `--no-cache` can be useful in some situations that require to not use cache when building the image.
```
docker build . -t api_nei [--no-cache]
```

Create the NEI-API service.
```
docker run -it -v `pwd`:/api_nei --network host --name api_nei api_nei
```

With this latter step, everything is completed. Check http://localhost:8000/docs to watch the API documentation with Swagger UI.

To restart the service afterwards, simply run `docker start pg_db` and `docker start -i api_nei` (the `-i` flag runs the container in interactive mode).
</details>


<details>
<summary>API Taça UA (api-tacaua)</summary>
<br>

*To be written...*
</details>


<details>
<summary>API Family (api-family)</summary>
<br>

*To be written...*
</details>



## Local Installation

This is a walkthrough on how to run each service in your **host machine**.

<details>
<summary>Web-App NEI (web-nei)</summary>
<br>

Download the node setup from version 18 (latest LTS version at the time).
```
curl -sL https://deb.nodesource.com/setup_18.x | sudo -E bash -
```

Then, install the node setup. After this, the command `node -v` should return the version 18.
```
sudo apt-get install nodejs
```

Install yarn using node:
```
sudo npm install --global yarn
```

On the service's root directory `/web-nei`, install the dependencies with this command. All dependencies will be saved in the node_modules folder, which will be created.
```
yarn install
```

Finally, to start the service run:
```
yarn start
```
</details>


<details>
<summary>API NEI (api-nei)</summary>
<br>

This API requires a connection to a PostgreSQL database. If you want to run this API stand-alone, it is recommended to creates a database inside a docker container, rather than in your host. For that, [install docker](#docker-installation) if needed and run this command to create the container. Once created, the container will always exist, unless it is specifically removed with `docker rm pg_db`. However, it might be necessary to start the container again when it stops (e.g. after a reboot). To start and stop the container, use docker [start|stop] pg_db.
```
docker run -d -p 0.0.0.0:5432:5432 -e POSTGRES_PASSWORD="postgres" --name pg_db postgres
```

Afterward, make sure to have poetry installed.
```
pip install poetry
```

Run this command to install all the Python dependencies required:
```
poetry install
```

You can use poetry to add more dependencies to the project (e.g. `poetry add uvicorn[standard]@latest`).<br>
Use `poetry show` to list all the dependencies.

Then, on the service's root directory `/api-nei`, run the FastAPI server via poetry with the Python command:
```
poetry run uvicorn app.main:app --reload
```
</details>


<details>
<summary>API Taça UA (api-tacaua)</summary>
<br>

The installation for this api is equal to the *API NEI installation*.
<details>


<details>
<summary>API Family (api-family)</summary>
<br>

*To be written...*
<details>




## Installation Troubleshooting

Common errors that can happen during installation.

**Poetry cannot install `psycopg2`**

If `psycopg2` cannot be installed with `poetry install` due to the error `pg_config executable not found`, the pyscopg2 documentation recommends installing the following packages:

```
sudo apt install python3-dev libpq-dev
```

**Address already in use**

If the FastAPI is having problems to start because the address is already in use, it is likely that another application is using the same port it is trying to use (the default port is **8000**). For a quick fix, kill the processes using that port with:

```
sudo fuser -k 8000/tcp
```
