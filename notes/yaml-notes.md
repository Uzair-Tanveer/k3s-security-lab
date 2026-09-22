# K3s Security Lab YAML Notes

## Purpose 
This file explains the purpose of each YAML file used in the single-node K3s security lab. It is meant as a study aid and documentation reference for reviewing the lab later and explaining the project during interviews.

## 1. Deployment.yaml

### What it does
The deployment file tells Kubernetes to run an application, keep it running, and recreate it if it fails.

### Why it Matters
This file is the core of the application. Without it, Kubernetes would not know what workload to run.

### Security Relevance
In a real environment, a deployment file may also include:
-non-root users
-resource limits
-read-only filesystems
-restricted capabilities


## 2. Service.yaml

### What it does
The service file gives the running pod a stable way to be reached inside the cluster.

### Why it matters
The service connects traffic to the correct pod. If the selector does not match the pod labels, the service will not have an endpoint.

## 3. Network-Policy.yaml

### What it does
The network policy controls which network traffic is allowed to reach pods in namespace.

### Why it matters
This is a security control. It helps reduce the attach surface by limiting who can talk to pods.

### Security Relevance
Network Policies are used in real enviornments to:
-segment workloads
-reduce exposure
-limit lateral movement
-enforce access control


## Key Kubernetes Concepts Learned

### Namespace
A namespace is like a folder inside Kubernetes. It keeps resources grouped and seperated from other workloads.

### Labels
Labels are key-value pairs used to organize and identify resources.


