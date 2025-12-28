# Monolithic Architecture vs Microservices Architecture

This document explains the differences between **Monolithic Architecture** and **Microservices Architecture** using simple real-world examples and relates them to modern cloud-native systems such as Kubernetes.

---

## Monolithic Architecture

**Definition:**  
Monolithic architecture is a software architecture where the entire application is built as a single, unified unit. All components are tightly integrated and deployed together.

### Example (Single Kitchen Analogy)

Imagine a restaurant with **one big kitchen** where everything happens:

- Taking orders  
- Cooking food  
- Serving customers  

All operations are handled in one place.

If one part of the kitchen fails, it affects the **entire restaurant**.  
For example, if the chef is sick or the stove breaks, the whole restaurant may stop functioning, impacting all customers.

### Key Characteristics
- Single codebase
- Single deployment unit
- Easier to develop and deploy initially
- Difficult to scale individual features
- High risk of complete system failure

---

## Microservices Architecture

**Definition:**  
Microservices architecture breaks an application into small, independent services. Each service is responsible for a specific function and can be developed, deployed, and scaled independently.

### Example (Food Delivery Analogy)

Consider food delivery platforms like **PickMe Food** or **Uber Eats**:

- There is no single kitchen
- Multiple restaurants prepare food independently
- Each restaurant represents a **microservice**

When you place an order:
- Each restaurant prepares its own part of the order
- The order is then combined and delivered to the customer

If one restaurant is busy or unavailable, the others continue working.  
For example, if the burger restaurant is overloaded, the rice and curry restaurant can still process orders without any issue.

### Key Characteristics
- Independent services
- Separate deployments
- Easy to scale individual services
- Better fault isolation
- Suitable for large and complex systems

---

## Key Differences

| Monolithic Architecture | Microservices Architecture |
|-------------------------|----------------------------|
| Single kitchen handling all tasks | Multiple specialized restaurants |
| Single deployment | Independent deployments |
| Hard to scale | Easy to scale |
| Single point of failure | Fault-tolerant |
| Best for small applications | Best for large, scalable systems |

---

## Relationship with Kubernetes

Kubernetes is designed to support **microservices architecture** by providing:

- Container orchestration
- Automatic scaling
- Service discovery
- Fault tolerance and self-healing
- Efficient resource management

Kubernetes makes it easier to deploy, manage, and scale microservice-based applications in production environments.

---

## Conclusion

- **Monolithic architecture** is suitable for small projects and simple applications.
- **Microservices architecture** is ideal for modern, scalable, and resilient systems.
- **Kubernetes** enables organizations to efficiently run microservices and achieve better scalability, reliability, and business agility.

---

# Kubernetes Overview

## Why Do We Need Kubernetes?
After Docker came into the picture, deploying applications on containers became much easier because containers are lightweight. However, managing a large number of containers in production environments introduced new challenges, such as container failures leading to significant business losses.  

Kubernetes addresses these challenges by automating tasks such as:  
- **Autoscaling** of containers according to peak or normal hours.  
- **Load balancing** across multiple containers.  
- **Automatic deployment** of containers to available nodes in the cluster.  
- **Self-healing** if containers fail.  

---

## Kubernetes Origins and Open Source
- **Created by:** Google in 2013  
- **Language:** Golang  
- Initially, Kubernetes was not open-source. In 2014, Google made it open-source and donated it to the **Cloud Native Computing Foundation (CNCF)**.  

---

## Languages Supported by Kubernetes
Kubernetes supports both **YAML** and **JSON** for configuration.

---

## Features of Kubernetes

1. **Autoscaling**  
   - Supports **horizontal** and **vertical** scaling for large-scale production environments, reducing downtime.  

2. **Auto Healing**  
   - If containers fail or stop due to issues, Kubernetes automatically repairs and restarts them.  

3. **Load Balancing**  
   - Distributes traffic between multiple containers efficiently.  

4. **Platform Independent**  
   - Works on any infrastructure: **on-premises**, **virtual machines**, or any **cloud environment**.  

5. **Fault Tolerance**  
   - Notifies about node or pod failures and creates new pods/containers quickly.  

6. **Rollback**  
   - Switch back to a previous version if needed.  

7. **Health Monitoring**  
   - Regularly checks container health and creates new containers if any fail.  

8. **Orchestration**  
   - Can manage containers running across different networks (on-premises, VMs, cloud) under a single cluster.  

---

## Alternatives to Kubernetes
- Docker Swarm  
- Apache Mesos  
- OpenShift  
- Nomad  
- And more


# Kubernetes Architecture

![Kubernetes Architecture](Images/k8s-archi.png)

Kubernetes follows a **client-server architecture** with Master (Control Plane) and Worker Nodes forming a Kubernetes Cluster. Multiple master and worker nodes can be added based on requirements.

### Control Plane
The control plane components—API Server, etcd, Scheduler, and Controller Manager—reside on the master node(s) and manage the cluster.

### Master Node
The Master Node controls the entire cluster and communicates with worker nodes. Its main components are:

1. **API Server:** Entry point for all Kubernetes commands (e.g., kubectl). It forwards requests to components that create or manage pods.  
2. **etcd:** Key-value database storing cluster state, including pod IPs, nodes, and configurations.  
3. **Controller Manager:** Monitors cluster state and sends instructions to maintain the desired state.  
4. **Scheduler:** Assigns workloads to worker nodes based on resources and requirements.  

**Real-world analogy:**  
In a food delivery company:  
- API Server = customer service desk  
- etcd = central database  
- Scheduler = dispatch manager  
- Controller Manager = operations manager  

### Worker Node
The Worker Node executes containers and communicates with the Master Node. Its main components are:

1. **Kubelet:** Monitors pods, replaces failed ones, and communicates with the API Server.  
2. **Kube-proxy:** Manages network traffic and load balancing based on cluster configuration.  
3. **Pods:** Smallest deployable units containing one or more containers.  
4. **Container Engine:** Provides runtime environment for containers (e.g., Docker, containerd).  

**Real-world analogy:**  
Worker nodes are like delivery riders: kubelet is the supervisor, the container engine is the vehicle, and kube-proxy ensures proper routing.

---

## Features of Kubernetes
- **Autoscaling:** Horizontal & vertical scaling reduces downtime.  
- **Auto Healing:** Automatically repairs and restarts failed containers.  
- **Load Balancing:** Distributes traffic efficiently.  
- **Platform Independent:** Works on any infrastructure (on-prem, VM, cloud).  
- **Fault Tolerance:** Detects failures and redeploys pods.  
- **Rollback:** Revert to previous versions if needed.  
- **Health Monitoring:** Regularly checks pod health.  
- **Orchestration:** Manages containers across different networks under one cluster.  

---

## Alternatives to Kubernetes
- Docker Swarm  
- Apache Mesos  
- OpenShift  
- Nomad  





📌 *This repository is part of a learning journey to understand Kubernetes core concepts and cloud-native architectures.*
