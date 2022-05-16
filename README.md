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

# Replication Controller
Capable of deploying additional PODs as needed.
## Sample YAML
![image](https://user-images.githubusercontent.com/42272776/110676258-c660bb00-81f9-11eb-888a-2a800948645e.png)

# Replica Set
New technology that replaces Replication Controller.
Spawns pods that wrap containers.
## Sample YAML
![image](https://user-images.githubusercontent.com/42272776/110676442-f90ab380-81f9-11eb-942e-e08b327bcaf5.png)

The replica set does the managing of the containers. If a container crashes, it automatically creates a new one.
![image](https://user-images.githubusercontent.com/42272776/110676590-2192ad80-81fa-11eb-8fc2-daf469d0b9c2.png)

## Scaling
![image](https://user-images.githubusercontent.com/42272776/110676915-877f3500-81fa-11eb-8d94-63b98cdd130e.png)

## Commands
![image](https://user-images.githubusercontent.com/42272776/110676987-9fef4f80-81fa-11eb-9443-aae5c9c7e831.png)

# Deployment

![image](https://user-images.githubusercontent.com/42272776/110679042-05dcd680-81fd-11eb-9778-53efde4ba55e.png)

![image](https://user-images.githubusercontent.com/42272776/110679118-1ee58780-81fd-11eb-9b25-a057f42a1b9e.png)

## Upgrades
![image](https://user-images.githubusercontent.com/42272776/110680530-bdbeb380-81fe-11eb-90b2-fd163fe2ec52.png)

## Rollbacks

![image](https://user-images.githubusercontent.com/42272776/110680422-99fb6d80-81fe-11eb-832e-7da795fb7523.png)

## Commands

![image](https://user-images.githubusercontent.com/42272776/110680458-a5e72f80-81fe-11eb-9f66-7ea600762899.png)

Hands-on
1. Deploy a sample app for a webservice interacting with a databas.


