# Python Docker Project Command Sheet.

This piece, is a simple sheet with commands to streamline the workflow process when working on Python projects and Docker.

## Python Basics

Some basic Python commands - especially project starters.

### 1. Create a virtual environment.

```shell
python -m venv env
```

### 2. Activate the virtual environment.

> windows: 

```shell
source env/Scripts/activate
```

> linux/mac:

```shell
source venv/bin/activate
```

E.g. - run from any directory on a Linux(Ubuntu) VM.

```shell
source /home/ubuntu/project-directory/venv/bin/activate
```

### 3. Check and ensure that the desired/created virtual environment is what you are currently logged on(especially in a case where the dependencies seem not to be getting installed or if they seem not to be reflecting in the requirements file after installation).

```shell
which python
```

### 4. Install all dependency in the project's requirements.txt file.

```shell
pip install -r requirements.txt
```

### 5. Update the current requirements.txt file - if/when necessary.

```shell
pip freeze > requirements.txt
```

## Docker 

Relevant Docker command, with template samples of how I use some of them.

### 6. Build a docker image.

```shell
docker build -t image-name .
```

### 7. Add a tag to a docker image.

```shell
docker image tag image-name docker-hub-user-name/remote-image-name:tag-name
```

### 8. Push a docker image to docker hub.

```shell
docker image push docker-hub-user-name/remote-image-name:tag-name
```


### 9. execute a bash shell for a running commands on a container**

```bash
docker exec -it container-id bash

# preferrably as root user below

docker exec -u root -it container-name bash
```

### 10. Inspect a Docker container to see important details - e.g. the container IP, and a lot more.

```shell
docker inspect container-id
```

### 11. Run a docker container(from a locally available image).

```shell
docker run -d -p desired-port:docker-port -e SECRET_ONE="secret_one" -e SECRET_TWO="secret_two" --name 
container-name local-image-name
```

### 12. Run a docker container(from a remote image).

```shell
docker run -d -p desired-port:docker-port -e SECRET_ONE="secret_one" SECRET_TWO="secret_two" --name container-name 
docker-hub-user-name/remote-image-name:tag-name
```

### 13. Run a docker container(from a remote image) using a local env file(cleaner and more secure)

```shell
docker run -d -p desired-port:docker-port --env-file .env --name container-name local-image-name
```
