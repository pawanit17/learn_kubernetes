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

### Kubectl

- kubectl run hello-minikube
- kubectl cluster-info
- kubectl get nodes

# PODs
Containers in a Kubernetes worker node are encapsulated inside a POD.
![image](https://user-images.githubusercontent.com/42272776/110517082-65b97b80-8130-11eb-9f5e-41cb17756ca3.png)

PODs usually have a single container. If the requests increase, we simply spawn a new POD in the same node or in another node.
This helps the cluster serve the growing number of user requests.
![image](https://user-images.githubusercontent.com/42272776/110517223-9699b080-8130-11eb-9ec4-9f7f58498fdf.png)

PODs over manual spin offs
![image](https://user-images.githubusercontent.com/42272776/110517550-027c1900-8131-11eb-9e76-de241d1812de.png)

# YAML
YAML is the language/syntax that is used for writing Kubernetes configurations.

