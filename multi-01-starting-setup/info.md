docker run --name mongodb --rm -d -p 27017:27017 mongo
 docker container prune

 docker build -t goals-node .
 docker run --name goals-backend --rm -d -p 80:80 goals-node



 frontend

 docker build -t goals-react .
 docker run --name goals-frontend --rm -d -p 3000:3000 -it goals-react
 docker network create goals-net

 docker run --name mongodb --rm -d --network goals-net mongo
  docker run --name goals-backend --rm -d -p 80:80 --network goals-net goals-node
  docker run --name goals-frontend --rm -p 3000:3000 -it goals-react


WIth volume 

 docker run --name mongodb -v data:/data/db --rm -d --network goals-net mongo
 docker run --name mongodb -v data:/data/db --rm -d --network goals-net -e MONGO_INITDB_ROOT_USERNAME=bayuaji -e MONGO_INITDB_ROOT_PASSWORD=secret mongo


 
docker run --name goals-backend -v "/Users/bayuaji/Documents/mini project/Self Development/Docker/multi-01-starting-setup/backend:/app" -v logs:/app/logs -v /app/node_modules  -e MONGODB_USERNAME=bayuaji --rm -d -p 80:80 --network goals-net goals-node
