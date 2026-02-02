# Kubernetes
Open Source system which automates container deployment tasks. Originally part of Google, but is now part of Cloud Native Computing Foundation (CNCF), basically speaking, it is a higher level abstraction over Docker.

## Features
* Automated rollouts, scaling, and rollbacks
* Service discovery, load balancing, network ingress
* Stateless and Stateful applications
* Storage Management
* Declarative State
* Works across environments
* Highly extensible

## Architecture
* Control Plane
  * The managing node over other worker nodes, talk with kubelet in each node to communicate
  * There can exist multiple at the same time for redundancy, similar to normal nodes
* Nodes
  * Worker nodes which can be used to deploy applications onto
  * Each node has a 'kubelet' which acts as the interface between the node's internal operations and the control plane
* Pods
  * Fundamental compute unit in k8s
  * Each pod contains multiple containers of the same function, and will all be scheduled to one node
  * Basically, each functionality of the application should have its own pod as the containers inside a pod are tightly-coupled
* Jobs
  * An object that attempts to create a set of Pods waits for them to terminate, and will retry until any failed Pods until a specified number have exited successfully
* Services
  * Services are used to expose Pods to the network. They allowed external access to Pods
* Labels
  * Labels are key/value pairs that are attached to objects, such as pods
  * Labels are intended to be used to specify identifying attributes of objects that are meaningful and relevant to users, but do not directly imply semantics to the core system.
* Namespaces
  * Namespaces isolate different groups of resources. They avoid name collisions by scoping the visibility of your resources.

```
Deployments -> ReplicaSets -> Pods -> Containers <- Docker Image
                                          /\
                                        Service
                                          /\
                                        Ingress
                                          /\
                                         User
```
