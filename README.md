# Shapeshift Eth Node

## Dependencies

Ansible 2.4.3.0 | Ansible Container 0.9.2 | Docker | Kubernetes

## Build Container

```
$ ansible-container build
```

## Run container locally 

```
$ ansible-container run
$ docker ps                             # find <CONTAINER_ID>
$ docker logs <CONTAINER_ID> --follow   # tail container logs
$ docker stop <CONTAINER_ID>            # stop container
```

## Tag image

```
$ docker tag shapeshift-eth-node:latest <DOCKER_HUB_NAME>/shapeshift-eth-node:latest
```

## Push image to registry

```
$ docker push <DOCKER_HUB_NAME>/shapeshift-eth-node:latest
```

## Deploy to kubernetes

Make sure you're signed into a cluster in which to deploy via `kubectl`

``` 
# this will deploy the following image: matthewberryhill/shapeshift-eth-node:latest
$ kubectl create -f k8/deploy.yaml
```

## Find deployed pod and tail logs

``` 
$ kubectl get pods                      # pod with *eth-node* prepended
$ kubectl logs <NAME_OF_POD> -f            
```
