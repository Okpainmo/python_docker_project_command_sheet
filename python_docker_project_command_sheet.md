# A Simple Sheet With Commands To Streamline The Workflow Process When Working On Python Projects With Docker.

## 1. Create a virtual environment.

```shell
python -m venv env
```

## 2. Activate the virtual environment.

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

## 3. Check and ensure the current virtual environment is what you are currently logged on(especially in a case where the dependencies seem not to be getting installed or if they seem not to be reflecting in the requirements file after installation).

```shell
which python
```

## 4. Install all dependency in the project's requirements.txt file.

```shell
pip install -r requirements.txt
```

## 5. Update the current requirements.txt file if necessary.

```shell
pip freeze > requirements.txt
```

## 6. Build a docker image.

```shell
docker build -t image-name .
```

## 7. Add a tag to a docker image.

```shell
docker image tag image-name docker-hub-user-name/remote-image-name:tag-name
```

## 8. Push a docker image to docker hub.

```shell
docker image push docker-hub-user-name/remote-image-name:tag-name
```

## 9. Run a docker container(from a locally available image).

```shell
docker run -d -p desired-port:docker-port -e SECRET_ONE="secret_one" -e SECRET_TWO="secret_two" --name container-name local-image-name
```

## 10. Run a docker container(from a remote image).

```shell
docker run -d -p desired-port:docker-port -e SECRET_ONE="secret_one" SECRET_TWO="secret_two" --name container-name docker-hub-user-name/remote-image-name:tag-name
```

## 11. Run a docker container(from a remote image) using a local env file(cleaner and more secure)

```shell
docker run -d -p desired-port:docker-port --env-file .env --name container-name local-image-name
```
