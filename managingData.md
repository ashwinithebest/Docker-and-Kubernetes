### Application (Code + environment)
written & provided by you
added to image and container and it is fixed Readonly

### Temporary App Data
Fetched / Produced in running Container
Stored in memory or temporary files
Dynamic and changing. but cleared regularly
Read + Write temporary

### Permanent App Data
Fetched / Produced in running container
Stored in files or a database
Must Not be lost if container stops /restarts
Read + Write permanently stored with volumes 

Problem : if we remove while stopping it the container all the data will be lost
Volumes are folders on your host machine hard drive which are mounted("made available, mapped) into containers

volumes persist if container shuts down.
containers can read- write data from volumes

### two type of External Datastorages
a defined path in the container is mapped to the created volume / mount 
e.g. /some-path on your hosting machine is mapped to /app/data
1. Volumes (Managed by docker)
 docker sets up a folder / pathon your host machine, exact location is unknown to us, Managed by docker volume commands.
 a. anonymous volumes
 b. named volumes- we can't create the named volume in dockerfile 
2. Bind Mounts (Managed by you)
 great for data which should be persistent but which you don't need to edit directly 

`docker run -p 3000:80 -v volumeName:/filepath`

# Bind Mounts
you define a folder / path on your host machine.
great for persistent and editable(by you) data.
as image is just a snapshot of cde, you can use bind mount to keep the updated code in the image as you make changes.
we have to setup the bind mount while running the container.
