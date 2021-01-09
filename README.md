# Docker
# To list all runing container
    docker container ls (new way) = docker ps (old way)
# To Show all containers (default shows just running)
    docker container ls -a

# To remove container
    doccker container rm {conainer ID}
# To run stop container
    docker container start {container ID}
# To stop container
    docker container stop {container ID}
# To run container with detached (-d) {run container in background}
    docker container run -d ubuntu sleep 30
# To run container and go inside to container (-it i=interactive, t=tty) 
    docker container run -it ubuntu /bin/bash
# To exit container but container keeps run, use => (ctrl + p + q), not => (ctrl+d) 
# To Delete all containers at once
    docker container rm $(docker container ls -aq)
# To show all information of container
    docker dontainer inspact {container ID}

#  ========================Port Maping and Forwording=============================