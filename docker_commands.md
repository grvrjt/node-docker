# commands

# create docker network
docker network create mongo-network

## start mongodb
docker run -d \
-p 27017:27017 \
-e MONGO_INITDB_ROOT_USERNAME=admin \
-e MONGO_INITDB_ROOT_PASSWORD=password \
--net mongo-network \
--name mongodb \
mongo

## start mongo-express
docker run -d \
-p 8081:8081 \
-e ME_CONFIG_MONGODB_ADMINUSERNAME=admin \
-e ME_CONFIG_MONGODB_ADMINPASSWORD=password \
-e ME_CONFIG_MONGODB_SERVER=mongdob \
--net mongo-network \
--name mongo-express \
mongo-express

## to build the image of app
1. create an empty repo on dockerhub.com
2. from the terminal 
   docker build -t grvsrjt/my-app:1.0 .
   docker login 
   docker push grvsrjt/my-app:1.0

## Docker Compose 
1. DOCKER
 docker logs <container_id>

2. DOCKER-COMPOSE
  docker-compose -f <file_name> up
  docker-compose -f <file_name> down
  docker-compose -f <file_name> stop

## Docker Volume 




## Docker Networking 
1. docker network inspect bridge 