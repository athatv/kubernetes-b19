# KUBERNETES

## What is Kubernetes?
- kubernetes is open source ochestration system for automating software deployment,scaling and management of containerized applications.
- kubernetes originally designed by Google 

## Why we use Kubernetes?
- kubernetes provide us services like autoscaling,self-autohealing/autorestart, loadbalancing, security management, multinodes, monitoring.
## Architecture of Kubernetes
- When we deploy kubernetes you get cluster.
- Cluster consist of master and slave (Master = Which give cammand, slave = Which obey the order of master)
- Kubernetes cluster consist of set of worker machine (worker nodes), that runs containerised application.

COMPONENTS OF CONTROL PLANE 
1) API - APPLICATION PROGRAMME INTERFACE
- The API server is a component of the Kubernetes control plane that exposes the Kubernetes API. The API server is the front end for the Kubernetes control plane.
- All the cumminication happens inside the cluster is through help of API.
- API server manage these API throughout the cluster.
- The main implementation of a Kubernetes API server is kube-apiserver. 
- kube-apiserver is designed to scale horizontally—that is, it scales by deploying more instances. You can run several instances of kube-apiserver and balance traffic between those instances.

2) ETCD -
- ETCD like a database.
- It holds the database in key-value formate
- ETCD is responsible to store state of cluster taht include no of nodes available, no of pods running on each nodes etc.

3) Scheduler -
- It is responsible to schedule cammand on perticular worker node.
- Control plane component that watches for newly created Pods with no assigned node, and selects a node for them to run on.
- Factors taken into account for scheduling decisions include: individual and collective resource requirements, hardware/software/policy constraints, affinity and anti-affinity specifications, data locality, inter-workload interference, and deadlines

4) controler manager -
- Controller manager is responsible for for managing actual state or desired state .
- It manage all controler in kubernetes cluster
- There are many different types of controllers 
    a) Node controller: Responsible for noticing and responding when nodes go down.
    b) Job controller: Watches for Job objects that represent one-off tasks, then creates Pods to run those tasks to completion.
    c) EndpointSlice controller: Populates EndpointSlice objects (to provide a link between Services and Pods).
    d) ServiceAccount controller: Create default ServiceAccounts for new namespaces.

COMPONENTS OF WORKER NODE 

1) Kubelets -
- The Kubelet is responsible for managing the deployment of pods to Kubernetes nodes.
- It receives commands from the API server (Scheduler) and instructs the container runtime to start or stop containers as needed
- Kubelet make sure that container are running in pod.

2) Kubeproxy - 
- A network proxy running on each Kubernetes node. 
- It is responsible for maintaining network rules on each node. 
- Network rules enable network communication between nodes and pods.
-  Kube-proxy can directly forward traffic or use the operating system packet filter layer

3) PODs
- Pods are simply the smallest unit of execution in Kubernetes, consisting of one or more containers, each with one or more application and its binaries
- POD are deployable entities of kubernetes.
- POD are rapper arround a container.

