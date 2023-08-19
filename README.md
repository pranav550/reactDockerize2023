# build file
docker build -t react-image .

# run file
-d = detached mode
-it = interactive mode
docker run --rm --name react-app -d -p 4000:3000 react-image

# list of container
docker ps

# kill the container
docker kill react-container

# volume
###windows check on port 4000####
docker run --rm --name react-app -e CHOKIDAR_USEPOLLING=true -d -p 4000:3000 -v %cd%\src:/app/src react-image

###linux check on port 4000#####
docker run --rm --name react-app -d -p 3000:4000 -v "$(pwd)/src":/app/src react-image

# check logs
docker logs containerId/container name

# enter into container
docker exec -it containerID/containername bash

# container remove
docker rm -f containerID/containerName

# image remove
docker rmi -f containerID/containerName

# remove all volumes
docker volume prune

# remove all coantainer and images
docker system prune -a

# run container with read only
###linux check on port 4000#####
docker run --rm --name react-app -d -p 3000:4000 -v "$(pwd)/src":/app/src:ro react-image

# docker compose

# run container using docker compose
docker-compose up -d --build

# stop the container
docker-compose down

# docker compose container run for dev
docker-compose -f docker-compose.yml -f docker-compose-dev.yml up -d --build

# docker compose container down for dev
docker-compose -f docker-compose.yml -f docker-compose-dev.yml down

# docker compose container run for prod
docker-compose -f docker-compose.yml -f docker-compose-prod.yml up -d --build

# docker compose container down for dev
docker-compose -f docker-compose.yml -f docker-compose-prod.yml down

<!-- 
# build file for dev 
docker build -f Dockerfile.dev -t docker-image-dev .

# build file for prod 
docker build -f Dockerfile.prod -t docker-image-prod . -->

<!-- # run container with prod
docker run --env-file ./.env -d -p 8080:80 --name react-app-prod docker-image-prod -->


