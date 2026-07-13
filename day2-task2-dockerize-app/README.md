# Day 2 - Task 2: Dockerize an Application

## Objective
Create a Dockerfile, build an image, and deploy a container locally.

## App
Static HTML/CSS/ site (static-site-docker), cloned from GitHub.

## Dockerfile
```dockerfile
FROM nginx:alpine
COPY . /usr/share/nginx/html
EXPOSE 80
```

## Build & Run
```bash
docker build -t static-site-docker .
docker run -d -p 8080:80 --name static-site-docker-container static-site-docker
docker ps
curl http://localhost:8080
```

## Verification
Container ran successfully, mapping host port 8080 to container port 80.
`curl` confirmed the site's HTML was served correctly by nginx.

## Screenshots
See `/screenshots` folder.

## Key Takeaway
Static sites need no runtime/dependencies inside the container - nginx:alpine
is enough to serve files directly, keeping the image small and the
Dockerfile trivial.