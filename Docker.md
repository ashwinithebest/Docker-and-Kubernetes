# what is docker ?
container is standardized unit of software
a package of code and dependecies to run that code 
same conatiner always yields exact same application and excution behaviour 
support for container is built into modern operating systems
Docker simplifies the creation and management of such containers.

# why containers?
why do we want independent standardized "application packages".
1. dev and prod are not same often as a runtime version might differ.
2. dev env might difeer within team we need reproducability 
3. clashing tools and versio/ between different projects (switching between projects)

# Virtual Machine vs containers
VM's are waste of space and are slow 
PROS - creates separated env, env-specific configurationsare possible, envconfig can be shared and reproduced reliably
CONS - redundant duplication, slow performance and boot time, reproducing in other vm is tricky.

APP a
LIBRARIES AND DEPENDENCIES
VIRTUAL OS
MACHINES OS


docker helps build ad manage containers
low impact on OS, very fast, minimal space usage
sharing, re-building and distribution is easy
encapsulated apps/env's instead of whole machine.

container A(libs, Deps , tools)
Docker Engine
OS Built-in /Emulated Container Support
MACHINE OS

why do we have to enable the hyper v and contianers to support  docker 1/

Docker Tools & building blocks
1. docker Engine
2. Docker Desktop (includes daemon and CLI)
3. Docker Hub
4. Docker Compose
5. Kubernetes

# Images and containers
images are the templates/blueprint for containers, contains code and runtime
container is runnning "unit of software".

### using prebuilt images 
sources e.g. docker Hub
docker run -it node >> expose an interactive seesion from inside the container to our hosting machine
can be used as a terminal to run basic node commands.

"""to run the container we need `docker run -p 3000:80 image_id`"""
3000 is the port for the server
80 is the eposed port by the container"""

# images are layer based Architecture 
whenever you build an image docker caches every instruction result and then when you ebuilt and image it uses the caches if no change is done
![image layer](Image%20Layer.png)

when one layer changes all the subsequent layers are also reexecuted

# attached and detached mode
docker run -p 8000:80 container_id - attached - foreground in the terminal
docker run -p 8000:80 -d container_id - detached - background
we can attach again to the container by 
`docker attach container-id`
`docker logs -f container-name`
to restart the cstopped container in attached mode
`docker run -a container_id`

# entering interactive mode 
atach docker will give output in the terminal but not the input.
-i and -t i.e. -it
`docker run -it container_id`
`docker start -a -i container_id`

`docker run --rm -p 3000:80 -d container_id` remove the container once the container is stopped

to name the container --name container 
container have name images have tag
docker build -t name:tag .

## sharing images - pushing it to docker hub or private registry
to change the name of the image 
`docker tag oldName newName`
docker login to login
docker logout to logout






