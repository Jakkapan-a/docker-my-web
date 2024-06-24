### How to crete a docker image
1. Create a Dockerfile
```Dockerfile
FROM nginx:alpine-slim
COPY ./public /usr/share/nginx/html
```

2. Build the image
```bash
docker build -t toodev/my-web:latest .
```
3. Run the image
```bash
docker run -d -p 80:80 toodev/my-web:latest --name my-web
```

4. Open your browser and go to http://localhost

### How to push the image to Docker Hub
1. Login to Docker Hub
```bash
docker login
```

2. Tag the image
```bash
docker tag toodev/my-web:latest toodev/my-web:latest
```

3. Push the image
```bash
docker push toodev/my-web:latest
```

### How to pull the image from Docker Hub
1. Pull the image
```bash
docker pull toodev/my-web:latest
```

2. Run the image
```bash
docker run --name my-web -d -p 80:80 toodev/my-web:latest 
```

### How to remove the image and container
1. Stop the container
```bash
docker stop my-web
```

2. Remove the container
```bash
docker rm my-web
```

3. Remove the image
```bash
docker rmi toodev/my-web:latest
```
### How to remove all images, containers, volumes, networks and cache
1. Stop all containers
```bash
docker stop $(docker ps -a -q)
```

2. Remove all containers
```bash
docker rm $(docker ps -a -q)
```

3. Remove all volumes
```bash
docker volume rm $(docker volume ls -q)
```

4. Remove all networks
```bash
docker network rm $(docker network ls -q)
```

5. Remove all images
```bash
docker rmi $(docker images -q)
```

6. Remove all cache
```bash
docker system prune -a
```



