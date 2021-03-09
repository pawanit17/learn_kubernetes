# Orchestration
Process of managing containers - spawning up and destroying them as needed.

## Orchestration Technologies
- Docker Swarm
- Kubernetes
- Mesos

## Benefits
- Highly available
- Traffic load balanced
- Scaling the number of nodes

## Architecture
Master node manages the cluster of servers called Worker Nodes.
- Master node has Kube-apiserver, etcd, controller and scheduler
- Worker node has kubelet agent which interacts with Master giving health information and container runtime - Docker.
![image](https://user-images.githubusercontent.com/42272776/110516161-3a825c80-812f-11eb-96cc-cbe85c123ca5.png)


### Components
1. API Server - For interaction
2. Etcd - distributed key value store
3. Kubelet - agent, that helps in knowing if a service is working as expected.
4. Container Runtime - Docker
5. Controller - notifies and brings up new nodes when existing ones are down
6. Scheduler - distributes work across nodes

![image](https://user-images.githubusercontent.com/42272776/110516235-4ec65980-812f-11eb-93c3-3a46ce5a6e0c.png)


### kubectl

- kubectl run hello-minikube
- kubectl cluster-info
- kubectl get nodes


