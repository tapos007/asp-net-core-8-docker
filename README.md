# important docker command

```` 
 docker ps                     ======== Lists all running containers    ====================
 docker ps -a                  ======== Lists all containers            ============================ 
 docker rm (container name/id) ======== delete a container              ============================
 docker start/stop/restart (container name/id)
 docker images
 docker pull
 docker logs
 docker network ls
 docker network create 
 
 
 -p for port
 -d for detached
 --name 
 -it interactive terminal
 
  logs (-f, -n)
  
  docker-compose -f docker-compose.yaml up/down -d
 
 
 
docker run -p 1499:1433 -d  \
-e "ACCEPT_EULA=Y" \
-e "MSSQL_SA_PASSWORD=Rcis123$.." \
--name my-sql-server123 \
--hostname my-sql-server \
--network aspnet-microservice \
-v abc:/var/opt/mssql \
mcr.microsoft.com/mssql/server:2022-latest


docker run --name my-redis -d  \
-p 6379:6379 \
--network aspnet-microservice \
redis
"ConnectionStrings": {
  "ApplicationDb": "Server=localhost,1499;Database=docker-db;Trusted_Connection=False;User ID=sa;Password=sa123$..A;MultipleActiveResultSets=True;TrustServerCertificate=true;",
  "MyRedisConStr": "localhost:6379"
},

docker run --name docker-tutorial \
-d \
-p 8085:8080 \
--network aspnet-microservice \
-e "ConnectionStrings__ApplicationDb=Server=my-sql-server123;Database=docker-db;Trusted_Connection=False;User ID=sa;Password=Rcis123$..;MultipleActiveResultSets=True;TrustServerCertificate=true;" \
-e "ConnectionStrings__MyRedisConStr=my-redis:6379" \
my-dotnet-image

https://localhost:8086/swagger
http://localhost:8085/swagger

docker run --name my-nginx13 -d \
-p 8090:80 \
-v nginx-static-sites:/usr/share/nginx/html \
nginx

docker image tag backendapi taposregistry.azurecr.io/cmf-backendapi
docker image push taposregistry.azurecr.io/cmf-backendapi:latest

docker run -d --restart unless-stopped redis
 
\\wsl$\docker-desktop-data\version-pack-data\community\docker\volumes 

```