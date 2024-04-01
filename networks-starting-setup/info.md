docker build -t favorites-node .
docker run --name favorites -d --rm -p 3000:3000 favorites-node
docker run mongo
docker run -d --name mongodb --network favorite-net mongo 
docker container inspect mongodb

docker container prune
docker network create favorite-net
docker network ls



docker run --name favorites --network favorite-net -d --rm -p 3000:3000 favorites-node