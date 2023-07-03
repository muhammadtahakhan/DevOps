# Kubernetes
for local testing install nimikube
command :
curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
sudo install minikube-linux-amd64 /usr/local/bin/minikube
# for testing cluster
==> minikube start
we can run minikube with deiifrent drivers
==> minikube start --driver=virtualbox
To make virtualbox the default driver:
-> minikube config set driver virtualbox
first we need to install virtual box first
start command will create vm in virtualbox

==> minikube ip (to check ip address of node)
==> minikube ssh (to access the node/ or you can de ssh docker@ip and password would be usertc)

# Setup Multinode kubernetes cluster on local
# Prerequisites
-> have root access to each serve
-> the servers have network connectivity to each other
-> each server has at least 2gb of ram and 2 CPU cores
-> you have atleast two ubuntu server 18.04 or higher
-> swap memeory should be off in all mechines


create three vm mechines and create same network for all of them, and install docker in all vms (always install n-2 or n-2 version of docker)

==> hree -h (to check swap memory as we need to disable swap an every node of cluster)
=> swapeoff -a (to off swap in nodes)
once mechine restated it will again turn on swap to off swap perminantuily
--> vim /etc/fstab (and comment out all swap lines)

# Architecture Overview
master node and worker node all of them have some small components
=> Master Node (API server, Controller Manager, Scheduler, Etcd =>(is database it store key value pair data))
=> Worker Node (kubelet, kube-proxy, container runtime)

# Command
-> apt-get install bash-completion (for auto complete)
in ubunut .profile file always executes once user logedin.

# Pods in kuberbetes
pod is smallest unit of kubernetes and it contain container or multiple containers
these container will be using same ip and port of pod
now creating pod
-> kubectl run firstpod --generator=run-pod/v1 --image=coolgourav147/nginx-custom (--generator is deprecated)
-> kubectl run firstpod --dry-run --generator=run-pod/v1 --image=coolgourav147/nginx-custom (to show status. it will run command on client will not send command to server)
-> kubectl get pods (to list down all pods . kubectl get {resource name})
-> kubectl get po -o wide (to show pods with nodes)
-> kubectl expalin pods|less (it will help in writing yml kind and versions)
-> kubectl describe pod {pode name, it also show how many times it regenerated or crashed}
-> kubectl get pods -w (it will watch all pods activity)

# Delete 
-> kubectl delete {resourcetype} {resource name}
# command chart
-> kubectl (get, describr, delete, label) (pod, namespace, replicaset, replicacontroller, deployment, configmap) {name}
->
# kubectl label
-> kubectl label pod firstpod env=testing (it will assign label to pod)
-> kubectl --overwrite label pod firstpod env=production 
-> kibectl label pod firstpod env- (-  sign will remove label)
-> kubectl label pods --all status=xyz (it will assign label to all pods)
-> kubectl get pods --show-labels (to list down pods status with labels)
# yaml for kuberbetes resource
basic components of yaml are: (information can find usind -> kubectl explain pod)

apiVersion: V1
kind: Pod
metadata:
    name:myfirstpod
    labels:
        env:prod
spec:
    containers:
        - name:containername
          inmage:coolgourav147/nginx-custom  

to create pods from yaml file
-> kubectl create -f yamlfilename --dry-run (to check yaml file syntex)
-> kubectl create -f yamlfilename
-> kubectl explain pod --recursive |less (show template of yaml file)
-> kubectl run firstpod --dry-run --generator=run-pod/v1 --image=coolgourav147/nginx-custom -o yaml (will create yaml template of runing this pod)
-> kubectl run firstpod --dry-run --generator=run-pod/v1 --image=coolgourav147/nginx-custom -o yaml > myfirstpod.yaml (will create yaml template of runing this pod and withh write on file)


-> kubectl apply -f {yaml file name} (it will create resource for you using yaml file)
->kubectl edit pod {podename} (it will open yaml file in editor where you can edit pod)
# differance between run, create and apply command










