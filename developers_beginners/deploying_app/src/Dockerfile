# Source: linuxhint.com

# FROM instruction chooses the parent image for Docker.
# This example uses Alpine.
# Alpine is a minimal Docker image very small in size
FROM python:3.8-alpine

# LABEL instruction creates labels.
# The first label is maintainer with the value Linux Hint.
# The second label is appname with the value Flask Hello. World
# You can have as many key-to-value pairs as you want.
# You can also choose any name for the keys.
# The choice of maintainer and appname in this example
# is a personal choice.
LABEL "maintainer"="visla" "appname"="Flask Hello World"

# COPY instruction copies files or directories,
# from the Docker host to the Docker image.
# You'll copy the source code to the Docker image.
# The command below copies the requirements file
COPY ./requirements.txt /app/requirements.txt

# WORKDIR instruction changes the current directory in Docker image.
# The command below changes directory to /usr/src/flask-helloworld.
# The target directory uses the environment variable.
WORKDIR /app

# RUN instruction runs commands,
# just like you do on the terminal,
# but in the Docker image.
# The command below installs Python, pip and the app dependencies.
# The dependencies are in the requirements.txt file.
# RUN apk add --update python py-pip
RUN pip install --upgrade pip
RUN pip install -r requirements.txt

# EXPOSE instruction opens the port for communicating with the Docker container.
# Flask app uses the port 5000, so you'll expose port 5000.
COPY . /app
EXPOSE 5000

# configure the container to run in an executed manner
ENTRYPOINT [ "python" ]

# CMD instruction runs commands like RUN,
# but the commands run when the Docker container launches.
# Only one CMD instruction can be used.
CMD ["view.py" ]