# Kubernetes
### Notes from Kubernetes: Up and Running
#### chapter 3. Deploying to Kubernetes Cluster

Options when it comes to Kubernetes cluster:
* Google Container Service (gloud)
* Azure Container Service (az acs)
* AWS 
    * Quick start for Kubernetes by Heptio
    * kops on github
    * Fargate (not in the book)
* Locally (minikube)

### Installing minikube

##### installing
* install [kubectl](https://kubernetes.io/docs/tasks/tools/install-kubectl/) (kubernetes command-line tool)

* install [VirtualBox](virtualbox.org)


* install [minikube](https://github.com/kubernetes/minikube) (a local kubernetes distribution)

##### verification
`$ kubectl get componentstatuses`

output should look like this
```
NAME                 STATUS    MESSAGE              ERROR
controller-manager   Healthy   ok                   
scheduler            Healthy   ok                   
etcd-0               Healthy   {"health": "true"}   
```

Components:
* **controller manager** runs various controller regulating cluster behaviour: e. g. ensuring replicas are healthy.
* **scheduler** places pod onto different nodes in the cluster
* **etcd** storage for cluster where API object stored

## Playing with minikube 

#####List all nodes
`$ kubectl get nodes` 
nodes separated into:
* master — contains containers that manage the cluster
    * API server
    * scheduler
    * etc.
* worker nodes — contains user containers

#####Get info and statistics from node
`kubectl describe <node>` 
There will be:
* information about operation of _node_
* Statuses about disk and memory sufficiency
* capacity information of the machine
* information about software on the node
* pod currently running on this node

## Cluster components

#### 