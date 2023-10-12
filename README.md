# Kubernetes-Guide
An open-source container orchestration system for automating software deployment, scaling, and management.

### Config files
Config files are yaml files that define the resources for our cluster

Fields:

Object Types:
- Pods: Runs one or more closely related containers

- Services: Sets up networking in Kubernetes Cluster
    - ClusterIP: Exposes a set of pods to other objects in the cluster
    - NodePort: Exposes a container to the outside world (only good for dev purposes)
    - LoadBalancer
    - Ingress
 
## Investigation resources

Get resources 
<pre>kubectl get yourobject</pre>

Describe resources
<pre>kubectl describe yourobject</pre>

## Apply resources

<pre>kubectl apply -f configurationfile.yaml</pre>

## Delete resources
<pre>kubectl delete -f yourobject</pre>
