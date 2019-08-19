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

Create a VM (Ensure that you have installed VirtualBox)
```bash
docker-machine create --driver virtualbox <vm name>
```

View basic information about a node
```bash
docker-machine env <vm name>
```

List the nodes in a swarm
```bash
docker-machine ssh <vm name> "docker node ls"
```

Inspect node in swarm
```bash
docker-machine ssh <vm name> "docker ndoe inspect <node ID>"
```

View join token
```bash
docker-machine ssh <vm name> "docker swarm join-token -q worker"
```

Open SSH session with the VM; type "exit" to end
```bash
docker-machine ssh <vm name>
```

Leaving the swarm
```bash
docker-machine ssh <worker name> "docker swarm leave"
docker-machine ssh <master name> "docker swarm leave --force"
```

List the VMs; asterisk shows which VM this shell is talking to
```bash
docker-machine ls
```

Start a VM that is currently not running
```bash
docker-machine start <vm name>
```

Connect shell to VM
```bash
eval $(docker-machine env <vm name>)
```

Deploy application to master of swarm; to be used when the shell is connected to the VM ; uses local `docker-compose.yaml` file
```bash
docker stack deploy -c <file> <app name>
```

Copy file to node's home dir and deploy application; used only if SSH is used to connect to the manager and to deploy the application
```bash
docker-machine scp docker-compose.yml <master name>:~
docker-machine ssh <master name> "docker stack -c <file> <app name>"
```

Disconnect shell from VMs, use native Docker
```bash
eval $(docker-machine env -u)
```

Stop all running VMs
```bash
docker-machine stop $(docker-machine ls -q)
```

Delete all VMs and their disk images
```bash
docker-machine rm $(docker-machine ls -q)
```


