# simple-node
A Containerized Node JS web app display helloworld

## Environemnt setup 
* Install Docker desktop
* Enable Kubernetes
* Setup local docker registry [Reference](https://docs.docker.com/registry/deploying/)
```shell
docker run -d -p 5000:5000 --restart=always --name registry registry:2
```

## Build docker image

```shell
docker build -t localhost:5000/hello-world-image .
```

## Push image to local container registry
```shell
docker push localhost:5000/hello-world-image 
```

## Create configmaps
```shell
kubectl create configmap file12-config --from-file=files-1.yml
kubectl create configmap file3-config --from-file=files-2.yml
```

## Deploy k8s pod
```
kubectl create -f deployment.yml
```


## Cleanup
* Remove docker registry
```shell
docker container stop registry
docker container stop registry && docker container rm -v registry
```