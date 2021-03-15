# Vgames

A web app to keep tracks of my videogames.

## Setup

To compile the main image: `docker-compose build --build-arg USER_ID=$(id -u) --build-arg GROUP_ID=$(id -g)`

or use:

`./scripts/compile_image.sh`

To run the app use:

docker-compose up

To use pgadmin to check postgres database, in the browser go to localhost:5050

default email : pgadmin4@pgadmin.org

Password: admin

You can change the default email and password using PGADMIN_DEFAULT_EMAIL PGADMIN_DEFAULT_PASSWORD inside a .env file in the root directory.

Project use Poetry in the docker image generation. To add a python package to container update pyproject.toml file with the new package and run:

`poetry lock`

That will generate a new `poetry.lock` file. Then build the image again.

To speedup build process and you are in linux, you can set the following env variables inside your shell

`export DOCKER_BUILDKIT=1`

`export OMPOSE_DOCKER_CLI_BUILD=1`
