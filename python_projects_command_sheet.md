# Python Projects Command Sheet.

This piece, is a simple sheet with commands to streamline the workflow process when working on Python projects.

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

