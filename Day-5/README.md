# Day 5 – Kubernetes Overview & Cluster Setup

## Drawbacks of Docker:
- Docker containers are not self-sufficient.
- They don't handle load balancing – responsible for managing application traffic.
- Will not handle auto-scaling – (scaling up server, CPU, memory).

To overcome this, Kubernetes was invented.

---

## Kubernetes: K8S

- **Containerization management tool**
- **Orchestration tool** – managing all objects
- Introduced by Google in 2013 and open-sourced initially.
- In 2014, Google donated K8S to CNCF (Cloud Native Computing Foundation).

### Nodes:
- **Worker Node**
- **Master Node**

### Features of Kubernetes:
- **Auto scaling** – scales up servers or resources when traffic increases.
- **Auto healing** – if any resource is deleted, it will auto heal the deleted resource.
- **Load balancing** – distributes traffic equally between servers.
- **Platform independent** – works on any platform and supports all operating systems.
- **Rollback** – allows you to revert to previous states.
- **Health Monitoring of containers** – monitors the health of containers.
- **Fault tolerance** – ensures the system functions properly when a node fails.
- **Orchestration** – manages all objects.

Since it provides 8 features, it is called **K8S**.

---

## Kubernetes Architecture:

### Cluster:
A combination of nodes.

1. **Master Node**:
   - **API Server** – Entry point/gate when a command is executed, the request goes first to the API server.
   - **ETCD** – Acts as a store to store all information/data of the cluster.
   - **Controller Manager** – Collects information and sends it to the API server.
   - **Scheduler** – Decides when and what task should be performed.

2. **Worker Node**:
   - **Kublet** – Creates pods and deploys containers inside the pods.
   - **K-Proxy** – Collects all network info.
   - **Pod** – The smallest deployable unit. Kublet provides/creates the pod.
   - **Container Engine** – Provides the runtime environment for running Docker containers.

---

## How to Create Kubernetes Cluster:

1. Go to **EC2** → Click on **Launch Instance** → Create a name and tag (your name) → Choose **Ubuntu OS** → Select **t2.medium** → Create a new key pair → Allow SSH traffic → Set memory to **25MB** → Click **Launch Instance**.

2. Run the following commands:
   ```bash
   sudo su
   apt update -y

## Replica Set in Kubernetes

To maintain a specific number of pods, Kubernetes uses ReplicaSets. A ReplicaSet ensures that the desired number of pod replicas are running at all times, even if some pods fail or get deleted.

### Summary:
- **Pod**: The smallest deployable unit in Kubernetes.
- **ReplicaSet**: Ensures that the desired number of pods are continuously running and maintains their availability.
