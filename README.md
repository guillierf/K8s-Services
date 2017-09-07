# K8s-Services

## Code from Kubernetes Webinar Series - Understanding Service Discovery
https://www.youtube.com/watch?v=NrzrpyMLWes

## Narrative for this demo
1. BUILD: build image locally on your laptop: docker build . -t <DOCKER_HUB_USER>/color  (then push the image to registry)

2. DEPLOY: run app on K8s cluster: kubectl create -f



## Build a Docker image from existing JAvaScript source code and push it to Docker Hub. Replace DOCKER_HUB_USER with your Docker Hub username.
```
cd Build
docker build . -t <DOCKER_HUB_USER>/color
docker login
docker push <DOCKER_HUB_USER>/color
```

## Launch the app
```
docker run <DOCKER_HUB_USER>/color
```



## Deploy the app to Kubernetes
```
cd ../Deploy
kubectl create -f color-pod.yml
kubectl create -f color-svc.yml
```

## Check that the Pods and Services are created
```
kubectl get pods
kubectl get svc
```


## Test the app by accessing the NodePort of one of the nodes.

```
kubectl get nodes
curl <NODE_IP>:31001 for RED
curl <NODE_IP>:31002 for GREEN
curl <NODE_IP>:31003 for BLUE
```









