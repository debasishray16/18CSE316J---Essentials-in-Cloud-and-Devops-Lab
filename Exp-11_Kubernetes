# Kubernetes

## Kubernetes for Windows

```bash
# To start kubernetes or minikube in Windows through Docker Driver
# Keep Docker Desktop open

mininkube start --driver=docker

# To get the status of the working nodes.
kubectl get node
```

```bash
# To know the details of the pods.
kubectl -- get pods -a
```

```text
    > kubectl.exe.sha256:  64 B / 64 B [---------------------] 100.00% ? p/s 0s
    > kubectl.exe:  50.38 MiB / 50.38 MiB [------] 100.00% 227.99 KiB p/s 3m47s
NAMESPACE     NAME                               READY   STATUS    RESTARTS        AGE
kube-system   coredns-7db6d8ff4d-kfskr           1/1     Running   0               5m2s
kube-system   etcd-minikube                      1/1     Running   0               5m14s
kube-system   kube-apiserver-minikube            1/1     Running   0               5m14s
kube-system   kube-controller-manager-minikube   1/1     Running   0               5m14s
kube-system   kube-proxy-q9ftq                   1/1     Running   0               5m2s
kube-system   kube-scheduler-minikube            1/1     Running   0               5m14s
kube-system   storage-provisioner                1/1     Running   1 (4m40s ago)   5m12s
```

```bash
kubectl cluster-info
```

## Kubenetes Context

```bash
# Current Context
kubectl config current-context

# To get all teh context information.
kubectl config get-contexts

# To change the context of cluster
kubectl config use-context "minikube"

# To rename the context name of cluster
kubectl config rename-context "minikube" "demo"

# To delete the context name of cluster
kubectl config delete-context "demo"
```

1. To do imperatively on the terminal

```bash
kubectl create deployment mynginx1 --image=nginx

kubectl delete deployment mynginx1
```

2. To do declaratively.

- Go to the directory and create a YAML file for deployment and management of cluster.

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: nginx-deployment
spec:
  replicas: 2
  selector:
    matchLabels:
      app: nginx
  template:
    metadata:
      labels:
        app: nginx
    spec:
      containers:
      - name: nginx
        image: nginx:1.14.2
        ports:
        - containerPort: 80

```

Navigate to directory in CLI terminal

```cli
cd C:\Users\Debasish Ray\Downloads
```

- Now, Type the command in CLI:

```bash
kubectl create -f deploy-example.yaml
```

## Namespaces

Namespaces are those that are used to easily identify the pods in the nodes. If the parent node namespace is deleted, then child namespaces would be deleted automatically and easily.

```bash
# To list all the namespaces
kubectl get namespace

# Shortcut of above CLI command
kubectl get ns

# To set the cuurent context to use a namespace
kubectl config set-conetxt --current --namespace=Production

# To create a namespace
kubectl create ns Deployment

# To delete a namespace
kubectl delete ns Production

# To list all pods in all namespace
kubectl get pods --all-namespaces
```

## Nodes

```bash
kubectl get nodes

kubectl describe node
```
