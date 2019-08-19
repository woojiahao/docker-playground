# Docker
The core concept of Docker is build once, run everywhere - once an image is created and uploaded to the remote repository, the image can be run and the instructions will be processed accordingly. 

This is incredibly useful since it means that the environment does not need to be set up multiple times to run.

## Cheatsheet
List Docker CLI commands
```bash
docker
docker container --help
```

Display Docker version and info
```bash
docker --version
docker version
docker info
```

Execute Docker image
```bash
docker run hello-world
```

List Docker images
```bash
docker image ls
```

List Docker containers (running, all, all in quiet mode)
```bash
docker container ls
docker container ls --all
docker container ls -aq
```

Create imge using the current directory's Dockerfile
```bash
docker build -t friendlyhello .
```

Run "friendlyhello" mapping port 4000 to 80
```bash
docker run -p 4000:80 friendlyhello
```

Run "friendlyhello" mapping port 4000 to 80 in detached mode
```bash
docker run -d -p 4000:80 friendlyhello 
```

Gracefully stop the specified container
```bash
docker stop <hash>
```

Force shutdown the specified container
```bash 
docker kill <hash>
```

Remove specified container from this machine
```bash
docker container rm <hash>
```

Remove all containers
```bash
docker container rm $(docker container ls -aq)
```

List all images on this machine
```bash
docker image ls -a
```

Remove specified image from this machine
```bash
docker image rm <image id>
```

Remove all images from this machine
```bash
docker image rm $(docker image ls -aq)
```

Log in this CLI session using Docker credentials
```bash
docker login
```

Tag <image> for upload to registry
```bash
docker tag <image> username/repository:tag
```

Upload tagged image to repository
```bash
docker push username/repository:tag
```

Run image from registry 
```bash
docker run username/repository:tag
```

List stacks or apps
```bash
docker stack ls
```

Run the specified Compose file
```bash
docker stack deploy -c <composefile> <appname>
```

List running services associated with an app
```bash
docker service ls
```

List tasks associated with an app
```bash
docker service ps <service>
```

Inspect task or container
```bash
docker inspect <task or container>
```

List container IDs
```bash
docker container ls -q
```

Tear down an application
```bash
docker stack rm <appname>
```

Take down a single node swarm from the image
```bash
docker swarm leave --force
```
