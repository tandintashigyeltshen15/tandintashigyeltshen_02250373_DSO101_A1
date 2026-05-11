## Docker

===============================================================================================

# A virtual Machine uses more space (in GB)
# Docker uses less space (in KB). It performs continuous integration and deployment.

# What is a docker?
> Docker is a tool that lets you run applications in containers.

# What is a container in docker?
> A container is like a small package that includes:

* your code
* dependencies (libraries, packages)
* runtime

So your app runs the same everywhere. 

# Docker Image
> Image is like a blueprint used to create a docker container.

# Docker Hub
> Docker Hub is an online cloud registry where developers store and share Docker images. It is Docker’s official container registry and hosts millions of public and private images.

# NGINX
> It is a high performance web server and reverse proxy server designed to handle large volume of concurrent connection efficiently.

> NGINX = “traffic controller for your website”

> It can handle thousand of users, improve speed and add security.

# Ansible
> Tool used to automate task on multiple computer at once.

> Ansible = “robot that sets up your system for you”

> It installs software automatically, sets up server, and deploys app.

# Hypervisor
> Layer of software that uses lightweight linux distribution supporting multiple virtual machines.

> Hypervisor = “manager that runs multiple computers inside one computer”

> It creates and runs virtual machines and manages hardware sharing.

# Most of the docker images are linked with linux commands.

## Basic  Commands 

> docker run --- start a container
> docker ps --- list containers
> docker ps -a --- list all containers
> docker stop --- stop a container
> docker rm --- remove a container
> docker images --- list images
> docker run --help --- Provide you with the manual
> docker rmi --- remove images
> docker pull --- Download images
> docker run -it --- Interactive mode
> docker daemon --- Internal core of a docker desktop. (Brain of a desktop)

# Run a image in docker
> docker run hello world 
Where hello world is the name of the image.

## Exit code

> Exit code or return code is a number that a program or process returns when it finishes running.

Exit Code        |    Meaning
                 |
    0            |   Success
    1            |   General error
   130           |   Terminated by ctrl + c (SIGNT)
   137           |   Killed (SIGKILL)
   143           |   Stopped (SIGTERM)

# To check the version
> docker --version

> cat /etc/*release*

1. cat 
> short for concatenant
> It simply prints the contents of files to the terminal

2. /etc/
> This is a system folder in Linux
> It stores configuration and OS-related files

3. *release*
> * is a wildcard (means “anything”)
> So this matches all files with “release” in their name

# Overall it means “Show me all files in /etc that contain OS version information”

> Because different Linux systems store version info in different files.
> Instead of checking one by one, this command:
* grabs all possible version files
* prints them together

> in short, It displays your Linux distribution name and version.

# How to go inside a container?

> docker run -it centos:7 bash

1. docker run → create & start a container
2. -i → interactive (keeps input open)
3. -t → gives you a terminal
4. centos:7 → uses CentOS 7 image
5. bash → starts a Bash shell inside the container

# What happens after running it?
> After running, you will see comething like;
[root@container-id /]#
> This means you are now inside the container, like a mini Linux system.

# What you can do inside this?
> Run Linux commands (ls, pwd, yum install, etc.)
> Install packages
> Explore the file system

# Container lifecycle (how container start and stop)

> docker run -d centos:7 sleep 20

1. docker run → create and start a new container
2. -d → run in detached mode (background)
3. centos:7 → use the CentOS 7 image
4. sleep 20 → run a command that does nothing for 20 seconds

> Here the container is going to run only for 20 seconds and then it goes back to exit.
> it cannot start to code unless exitted.

# Terminate in docker
> In docker, terminate means to stopping or removing a container.

> docker stop sweet_thompson
* where sweet_thompson is container name.

# How to remove a container using ContainerID

> docker rm 98221d9ff169
* where  98221d9ff169 is the container id

# How to remove a container using container name

> docker rm hopeful_ramen
* where hopeful_ramen is the container name.

# Removing containers using 3 letters of CID

> docker rm 9e5 873 a89 ca8 bf3

> this allows to remove conatainers fast instead of removing each container by their full name or full CID.

# Taking the image(file) without touching the container

> downloading a Docker image without running a container

1. List the containers first
> docker run ps -a

> You will see something like:
CONTAINER ID   IMAGE      STATUS
abc123         centos:7   Up 10 seconds

2. Run a command inside a container
> docker exec CID cat /etc/os-release

* docker exec → runs a command inside a running container
* cat /etc/os-release → shows OS version inside that container

> It Check which Linux OS is inside this container
> This only works if the container is running.
> If it’s stopped, you’ll get an error.

3. Open a duplicate host: New terminal - Docker stop
> Get out of the running container using ctrl + c

