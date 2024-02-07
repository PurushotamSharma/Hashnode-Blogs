---
title: "Kubernetes In One Blog"
datePublished: Thu Feb 09 2023 12:26:07 GMT+0000 (Coordinated Universal Time)
cuid: clsbgs8v0000b08l357m2g8np
slug: kubernetes-in-one-blog-180ca9266837
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1707290670058/07a94074-2435-4790-8530-58a386bf6250.png

---

Hello, everyone welcome to my blog.I hope you all are doing well, that’s great. In this we will cover about our today’s topic Kubernetes.

Let’s Start……without wasting time..

When you listen about Kubernetes, the first question in your mind came that what is Kubernetes. And when you go for any DevOps interview the first question HR will ask you have you know about Kubernetes.Let’s discuss about it why it is so important in DevOps Journey.

> **What is Kubernetes?**

Kubernetes is an open source container management tool that automates container Deployment , Scaling and load balancing.

It schedules runs and manages isolated containers that are running on virtual or physical cloud machines.

All the top Cloud Provider support Kubernetes.

Is is also known as K8s.

> **Some History about K8s**

First of all Google developed an internal system called **‘Borg’ (**l**ater named Omega)** to deploy and managed thousands of google applications and services on their cluster.

In 2014, google introduced Kubernetes an Open source platform written in ‘Golang’ and later donated to CNCF (Cloud Native Computing Foundation).

> **Online Platform for Kubernetes**

### . Kubernetes Playground.

### . Play with K8s.

### . Play with Kubernetes Classroom.

> **Cloud Based Kubernetes Services**

1.  GKE \[Google Kubernetes Engine\]
2.  AKS \[Azure Kubernetes Engine\]
3.  Amazon EKS \[Amazon Elastic Kubernetes Service\]

> **Features of Kubernetes**

1.  Orchestration :- Clustering of any number of containers running on different networks.
2.  Auto Scaling :- \[Vertical and Horizontal\]
3.  Auto Healing
4.  Load Balancing
5.  Platform Independent
6.  Fault Tolerance
7.  Rollback
8.  Health Monitoring of Containers
9.  Batch Execution

I hope above all things are clear for you to understand. Now we will Discuss About Kubernetes Architecture.

### Kubernetes Architecture:

The Kubernetes environment consists of a control plane (or the master), a distributed storage system (etcd) that keeps the cluster state consistent, and any number of cluster nodes, or Kubelets. Kubernetes conforms to a client-server architecture, with the master installed on one machine and the nodes on separate machines.

Read more: [Understanding Kubernetes Architecture and Its Use Cases](https://www.simplilearn.com/tutorials/kubernetes-tutorial/kubernetes-architecture "Understanding Kubernetes Architecture and Its Use Cases")

While it’s possible to have multiple masters due to high availability demands, the accepted default setup features one master server that works as a point of contact and controlling node.

Kubernetes architecture must follow these three principles:

*   It’s secure, abiding by the most current security best-practices at multiple levels (application, cluster, and network)
*   It’s easy to use, operable with only a few simple commands
*   It’s highly portable, running on any mainstream Linux distribution, either bare metal or virtual machine processors and different cloud providers (AWS, Azure, Google Cloud). It also allows new container run times and supports workloads across multi-cloud and hybrid environments.

Kubernetes’ architecture consists of various components, which we will devote more time to in the next section.

Here is an architectural illustration of Kubernetes, shown courtesy of [Platform9](https://platform9.com/wp-content/uploads/2019/05/kubernetes-constructs-concepts-architecture.jpg "Platform9").

Here’s a review of the fundamental concepts of Kubernetes architecture.

*   Pod. A group of containers
*   Labels. Used to identify pods
*   Kubelet. Container agents responsible for maintaining pod sets
*   Proxy. Pod load balancers that help distribute tasks
*   Etcd. A metadata service
*   CAdvisor. Monitors resource performance and usage
*   Replication controller. Manages pod replication
*   Scheduler. Schedules pods in worker nodes

> **Working with Kubernetes:**

We create a Manifest (.yml file)

Apply those to cluster (to master) to bring it into desired state.

POD runs on a node which is controlled by master.

> **Role of Master Node:**

Kubernetes cluster contains container running or Bore Metal/ VM instances / cloud instances.

Kubernetes designates one or more of these as a master and all others as workers.

The master is now going to run a set of K8s processes. These processes will ensure the smooth functioning of the cluster. These process are called the Control Plane.

Can be Multi-Master for high availability.

Master runs control Plane to run cluster Smoothly.

### **Components of Control Plane**

1.  API Server:-

For all Communication

This API server interacts directly with the user (i.e. we apply .yml or .json manifest to API-Server)

This API-Server is meant to scale automatically as per load.

API -Server is the front end of the control plane.

2\. etcd:-

Store metadata and status of the cluster.

etcd etcd is a consistent and high available store.

Source of touch for cluster state.

**etcd has the following features**

a. Fully Replicated :- The entire state is available on every node in the cluster.

b. Secure:- Implements automatic TLS with optional client- certificate authentication.

c. Fast :- Benchmarked at 10000 writes per second.

3\. Schedular :-

When users request to the creation and management of pods, schedular is going to take action on these requests.

Handle POD creation and management.

Schedular match or assign any node to create and run pods.

A Schedular watches for newly created pods that have no node assigned for every pod that the schedular discovers, the schedular becomes responsible for finding the best node for that pod to run.

The schedular gets the information for hardware configuration files and schedules the pods on nodes accordingly.

4\. Controller-Manager

Make sure the actual state of the cluster matches the desired state.

→ Two possible choices for controller manager —

If K8s is on the cloud, then it will be a cloud controller manager.

If K8s is on non-cloud, then it will be kube-controller-manager.

### **Components on the master that runs the controller**

**Node Controller :-**For checking the cloud provider to determine if a node has been detected in the cloud after it stops responding.

**Route-Controller →:-**Responsible for setting up a network, and routes on your cloud.

**Service-Controller :-** Responsible for load Balancers on your cloud against services of type Load Balancer.

**Volume-Controller :-** For creating, attaching, and mounting volumes and interacting with the cloud provider to orchestrate volume.

> **Nodes (Kubelet and Container Engine)**

*   Node is going to run 3 important pieces of software/process.

> **Kubelet**

*   The agent running on the node.
*   Listens to Kubernetes master (eg- Pod creation request).
*   Use port 10255.
*   Send success/Fail reports to master.

> **Container Engine**

*   Works with kubelet
*   Pulling images
*   Start/Stop Containers
*   Exposing containers on ports specified in the manifest.

> **Kube-Proxy**

*   Assign IP to each pod.
*   It is required to assign IP addresses to Pods (dynamic)
*   Kube-proxy runs on each node & this makes sure that each pod will get its unique IP Address.
*   These 3 components collectively consist of ‘node’.

> **POD**

*   The smallest unit in Kubernetes.
*   POD is a group of one or more containers that are deployed together on the same host.
*   A cluster is a group of nodes.
*   A cluster has at least one worker node and a master node.
*   In Kubernetes, the control unit is the POD, not the containers.
*   Consist of one or more tightly coupled containers.
*   POD runs on a node, which is controlled by the master.
*   Kubernetes only knows about PODs (Does not know about individual containers).
*   Cannot start containers without a POD.
*   One POD usually contains One Container.

> **Multi Container PODs**

*   Share access to memory space.
*   Connect using Localhost <Container-Port>
*   Share access to the Same Volume.
*   Containers within POD are deployed in an all-or-nothing manner.
*   The entire POD is hosted on the same node (Scheduler will decide which node).
*   There is no auto-healing or scaling by default.

> **Higher-level Kubernetes Objects**

*   **Replication Set →** Auto scaling and auto-healing.
*   **Deployment →** Versioning and Rollback.
*   **Service →** Static (Non-ephemeral) IP and Networking.
*   **Volume →** Non-ephemeral storage \[Ephemeral → Storage outside the node\]