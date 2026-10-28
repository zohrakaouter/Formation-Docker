Docker:
1) Build system: 1) from dsl or, from sources
2) aset of rest apis , 

an image ;snapshot of a file system not mutable

a container ??  mutable
container is layered from the immutable image, temporory :: filesystem , network stack , 

https://www.hostinger.com/tutorials/docker-image-vs-container/?utm_source=google&utm_medium=cpc&utm_id=20586398874&utm_campaign=Generic-Tutorials-DSA-t2|NT:Se|Lang:EN|LO:FR&utm_term=&utm_content=750690801773&gad_source=1&gad_campaignid=20586398874&gbraid=0AAAAADMy-hanNKlfZh3HYbPdyeLskC2Dk&gclid=CjwKCAjw9PvWBhAxEiwAddzYyUEBNeEgO37Y0Ghcz_EkM8MMwdIYWhaEE05ELThvTmslEKAOSfiVARoCcLkQAvD_BwE

docker contaniners can be run in rootful mode or in rootless mode , difference?

inside the container: becareful to run untrusted processes au root

- alternatives for docker in macos linux: Colima.
- quelqu'un asked about "flatpak" which is for linux? they talked about its differences with docker

- Now i get an image, how to manipulate a container:
Lifecycle ( diagramme d'état)
-run a container, stop it :p kill it, or remove it
- whiile running we can pause it , we can create it ( it will be in stopped not running)
so create /run an image, pause stop a container

-detach/ detach
- interact or not with the container:
'-t' ?
'-i' the container runs in interactive mode (pseudo terminal)
- pay attentation to stop the terminal and stop the container
- diff container vs image , we can commit them later
- 
Part 2: exercices .
Part 3:

- input/output:
--mount, type: bind (mount disk volumes in the container), ro option: read only, type: bind-create-src , ro option is usefull for config file ( we need to read them not to edit them)
- if you mount a volume in a container, its content in the disk will be hidden the time it is mounted ( to check)
- docker network, the docker container is not accessible from outside unless it publishes a tcp port

Part 3
Part4:
docker images:
deletion rmi, tags, layers

-----------------------------
- docker build creates a new image from a Dockerfile — a text file with instructions on how to build your image.
- the input of a build is " a context"
- Builder instructions --
- multi-stage build , it is used to optimize the image size
- I looked to how to dockerize my app, we start from a public ? image (base) to add layers on it
- build multiple images: build command for each one or bake command
- 

Security part :
-isolate container/host , container/container
- the container is run in rootful mode by defaut
- possibility: run as an ordinary user
- disable privilege escalation flag no new privileges during the container execution
- reduce root privileges : capabilities,seccomp, apparmor

- run the docker inside a VM: hypervisors