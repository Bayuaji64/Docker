# Docker

docker run build .
docker run -p 8000:80 [id container]
docker run -p 8000:80 -d --rm [id container]
docker run -p 8000:80 -d[id container] 
docker run -it[id container] 
docker start -a[id container] 
docker logs -f[id container] 

docker start -a -[id container]i
docker stop
docker rmi[id container]  

docker rm

docker image inspect [id container]  

docker cp [name file baru] ex: dummy/, [id image]   

 docker run -p 3000:80 -d --name [nama custom] [id image]   

 docker build -t [nama_custom:nama_version].
 docker run -p 8000:80 -d --rm --name[nama_cointainer] [nama_images:tag]

