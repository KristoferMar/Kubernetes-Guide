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

Apply whole directories with yaml files
<pre>kubectl apply -f directory</pre>

## Delete resources
<pre>kubectl delete -f yourobject</pre>


## Database related

### Volumes
"Volume" in generic container terminology
- Some type of mechanism that allows a container to access a filesystem outside itself

"Volume" in kubernetes
- An object that allows a container to store data at the pod level (INSIDE the pod)
- If the entire pod crashes the volume is lost also

"Persistent Volume"
- An object that allows us to store a volume outside the pod
- If the entire pod crashes the volume is NOT lost

"Persistent Volume Claim"
- An object that "fabricates" and creates the required volume on the fly.
- It claims space ahead of time