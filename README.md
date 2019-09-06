# Introduction

The repo is a fork of:
https://github.com/disney/meteor-base

The only addition is the the minikube folder, which contains the manifests to get it working on Kubernetes:
https://github.com/andypavia/meteor-base-kubernetes/tree/master/src/minikube


## Instructions

Make sure your computer has docker and minikube installed.

On the terminal session run:
```
eval $(minikube docker-env)
```

To build the image, run:
```
docker build -t meteor-app .
```

To deploy to Kubernetes, use the following command from the root folder:
```
kubectl apply -f minikube
```


You can see it woking on your localhost by applying:
```
kubectl port-forward svc/meteor-app 3000:3000
```
