# build file

docker build -t react-image .

# run file

-d = detached mode
-it = interactive mode
docker run --rm --name react-container -d -p 3000:3000 react-image

# list of container

docker ps

# kill the container

docker kill react-container

# volume

# its loading slow

docker run --rm --name react-container -it -p 3000:3000 -v %cd%:/app react-image

docker run --rm --name react-container -d -p 3000:3000 -v %cd%:/app react-image

docker run --rm --name react-container -e CHOKIDAR_USEPOLLING=true -d -p 4000:3000 -v %cd%:/app react-image

# check logs

docker logs containerId/container name

# enter into container

docker exec -it containerID/containername bash
