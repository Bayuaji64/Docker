 docker build -t feedback-node .


 docker run -p 3000:80 -d --name feedback-app --rm feedback-node
 docker run -p 3000:80 -d --name feedback-app feedback-node

 docker build -t feedback-node:volumes .

 docker run -d -p 3000:80 --rm --name feedback-app feedback-node:volumes

 docker run -d -p 3000:80 --rm --name feedback-app -v feedback:/app/feedback feedback-node:vol
umes

docker run -d -p 3000:80 --rm --name feedback-app -v feedback:/app/feedback -v "/Users/bayuaji/Documents/mini project/Self Development/Docker/data-volumes-01-starting-setup:/app" -v /app/node_modules feedback-node:volumes

docker run -d -p 3000:80 --rm --name feedback-app -v feedback:/app/feedback -v "/Users/bayuaji/Documents/mini project/Self Development/Docker/data-volumes-01-starting-setup:/app" -v /app/node_modules feedback-node:volumes          

 atau

 docker run -d -p 3000:80 --rm --name feedback-app -v feedback:/app/feedback -v $(pwd):/app -v /app/node_modules feedback-node:volumes

 jika read only 


docker run -d -p 3000:80 --rm --name feedback-app -v feedback:/app/feedback -v "/Users/bayuaji/Documents/mini project/Self Development/Docker/data-volumes-01-starting-setup:/app:ro" -v /app/node_modules -v /app/temp feedback-node:env 

docker rmi feedback-node:volumes

docker stop feedback-app
docker start feedback-app



docker stop feedback-app

CONTOH PENGGUNAAN ENV
docker run -d -p 3000:8000 --env PORT=8000 --rm --name feedback-app -v feedback:/app/feedback -v "/Users/bayuaji/Documents/mini project/Self Development/Docker/data-volumes-01-starting-setup:/app:ro" -v /app/node_modules -v /app/temp feedback-node:env 



docker run -d -p 3000:8000 --env-file ./.env --rm --name feedback-app -v feedback:/app/feedback -v "/Users/bayuaji/Documents/mini project/Self Development/Docker/data-volumes-01-starting-setup:/app:ro" -v /app/node_modules -v /app/temp feedback-node:env 

 docker build -t feedback-node:web-app .