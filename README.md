# Kubernetes-Guide
An open-source container orchestration system for automating software deployment, scaling, and management.

### Config files
Config files are yaml files that define the resources for our cluster

Fields:

Object Types:
- Pods: Runs one or more closely related containers

- Services: Sets up networking in Kubernetes Cluster
    - ClusterIP
    - NodePort: Exposes a container to the outside world (only good for dev purposes)
    - LoadBalancer
    - Ingress