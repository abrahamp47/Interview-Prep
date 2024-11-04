2024-09-13 12:03

Status:

Tags: [[Kubernetes]]

# Kubernetes Core Concepts

Kubernetes provides a framework from which we can run distributed systems resiliently by automating scaling and deployment of your applications

The main downside is that it is missing lot of specific pieces of functionality which prevents kubernetes from being a classic turnkey solution.

For Eg - it doesnt include method on how services speak to each other

## Core Components of Kubernetes

### Containers

![[Screen-Shot-2019-05-06-at-8.54.32-AM-768x708-1.webp | 300]]

Containers are a stand-alone, executable piece of software that includes everything it needs to run itself independently such as code and external dependencies. 

This ensures that the containers are identical regardless of the environment and context its running on. It is achieved using an Linux Kernel API called cgroup, which provide high amount of isolation without the performance hit of virtualised environments.

### Pods

Pods are a collection of containers, it has shared storage and network with specification on how to run them. Each pod has its own ip address and container within it share the ip address and ports, they can find each other using localhost.

### Replicaset

A replicaset basically run a n number of pods based on a template, so if we want to scale the number of pods in an environment we can use replicaset. They arent ussed directly usually.

### Service

Service is a way to reference a individual pods by providing an abstract over it and provide a addressable method to communicate with the pods.

#### 1. Cluster IP Service

A ClusterIP service in Kubernetes provides a stable virtual IP address (Cluster IP) to the service, allowing internal communication between various parts in the Kubernetes cluster, it exposes a set of Pods within the cluster to other objects in the cluster.

#### 2. Node Port Service

A NodePort service in Kubernetes is a type of service that allows a group of Pods accessible to external customers on an allocated port on all cluster nodes.

#### 3. Load Balancer service

An external load balancer is automatically provided by a LoadBalancer service in Kubernetes to distribute incoming traffic between the Pods when a group of Pods are accessible to the outside world.

#### 4. External Name Creation Service

An ExternalName service in Kubernetes works as an alias which allows pods inside the cluster to contact services outside cluster using a user-defined DNS name. External name provides DNS-based service discovery to map a service to an external DNS name.

### Deployment

Deployments helps to manage replicasets and is an easy way to deploy applications, the deployment controller will create required components

### ConfigMap

It allows to mount configuration files into a Pod as a env variable or as a file system mount from which Kubernetes can reference and build application as per configuration.

### Secrets

Similar to ConfigMaps, but handles sensitive data that cant be exposed

### Daemonset

Daemonset ensures that all Nodes run a specific Pod, we use Taints to ignore certains Nodes

### Ingress

In a normal Kubernetes setup, we can only access the pods and services within the kubernetes clusters. Ingress controllers help us route traffic from external and allows inbound connections to the cluster

 We usually use Nginx for this, it also helps in load balancing, terminate TLS and provide external URLs


# References


