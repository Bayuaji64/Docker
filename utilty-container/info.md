 docker run -it -d node

  docker exec -it goofy_keller npm init -y
  docker run -it node npm init -y 

  docker build -t node-util .
  docker run -it -v "/Users/bayuaji/Documents/mini project/Self Development/Docker/utilty-container:/app" node-util npm init -y

  docker build -t mynpm .

  docker run -it -v "/Users/bayuaji/Documents/mini project/Self Development/Docker/utilty-container:/app" mynpm init -y
  docker run -it -v "/Users/bayuaji/Documents/mini project/Self Development/Docker/utilty-container:/app" mynpm install 
  docker run -it -v "/Users/bayuaji/Documents/mini project/Self Development/Docker/utilty-container:/app" mynpm install express --save
  
  docker-compose run --rm npm init -y