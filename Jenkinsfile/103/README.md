# 103

## Run Docker containers for build stages
###### Be able to bring any container on Jenkins pipeline and actually running it on jenkins,	is great!. 
###### Because all of sudden I no longer have to set env variables for build tools, other miscs tools either.
###### Now this will reduces the amount of Global Tool Configuration inside Jenkins!

###### docker.image(name).inside { commands } runs all commands inside that container!

###### When running the above command it also changes the WORKDIR to jenkins job workspace using -w 

###### MOST IMPORTANTLY; creates a volume in current workspace dir and mounts it to container workspace dir that it creates

###### SOOOO whatever build artifacts are being created by docker container are actually being saved on host, but host is not running those build commands ( becase host does not have build tools configured! )

###### Running Containers inside pipeline

###### docker.image('name').run('run_args')
	
###### And since this runs a container, you can store the returned container of that command in a variable containerVar = docker.image('name').run('args')

###### With the container Object stored in variable after running the contaier, you get access to few other container methods; Likel .id or .stop()

###### def containerID = containerVar.id
###### containerVar.stop() 