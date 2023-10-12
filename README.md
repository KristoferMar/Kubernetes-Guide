# Kubernetes-Guide
An open-source container orchestration system for automating software deployment, scaling, and management.

### Config files
Config files are yaml files that define the resources for our cluster

Fields:

Object Types:
- Pods: Runs one or more closely related containers

- Services: Sets up networking in Kubernetes Cluster
    - ClusterIP     : Exposes a set of pods to other objects in the cluster
    - NodePort      : Exposes a container to the outside world (only good for dev purposes)
    - LoadBalancer  : Legacy way of getting network traffic into a cluster
    - Ingress       : Exposes a set of services to the outside world

Secrets: Securely stores a piece of information in the cluster, such as a database password
 
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

# Secrets
We create all secrets manually 
<pre>kubectl create secret generic 'secret_name' --from-literal key=value</pre>


# Ingress
There are two different kinds of ingress controllers avaiable and there is a big difference between them

ingress-nginx: A community led project
- github.com/kubernetes/ingress-nginx

kubernetes-ingress: A project led by the company nginx
- github.com/nginxinc/kubernetes-ingress

# Helm
Helm is a program we can use to administer third party software in our cluster.


Install: sudo dnf install helm

https://helm.sh/docs/intro/install/#from-script


# RBAC
Role Based Access Control

- Limits who can access and modify objects in our cluster
- Enabled on Google Cloud by default
- Tiller wants to make changes to our cluster, so it needs to get some permissions set


# Certmanger
Used to manage SSL Certificates
<a>github.com/jetstack/cert-manager</a>

Install via helm 

Install repo
<pre>helm repo add jetstack https://charts.jetstack.io</pre>

Update repo
<pre>helm repo update</pre>

Install cert-manager
<pre>helm install cert-manager jetstack/cert-manager --namespace cert-manager --create-namespace --version v1.8.0 --set installCRDs=true</pre>

### Certificate
Object describing details about the certificate that should be obtained.

### Issuer
Object telling cert Manager where to get the certificate from.