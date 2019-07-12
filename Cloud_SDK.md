# Google-Cloud

#Interactive installation (Google Cloud SDK installer)
#For Linux:
#Install Python
sudo app-get install python2.7
curl https://sdk.cloud.google.com | bash
#Restart your shell
exec -l $SHELL
#Run gcloud init to initialize the gcloud environment
gcloud init

# Set to default
export PS1='$'
gcloud components list
gcloud init

# Setting up of GKE
gcloud config set compute/zone us-central1-a
gcloud config set compute/region us-central1
# To create a k8s cluster
gcloud container clusters create <Cluster_Name> --num-node 1
# To view list of instances
gcloud compute instances list
# To run a container
kubectl run wordpress --image=tutum/wordpress --port=80
# To view the pod and it's status
kubectl get pods
# To expose the pod
kubectl expose pod <Pod_Name> --name=wordpress --type=LoadBalancer
# To view and describe the services
kubectl describe services <service_name>

# Command to run the container image
kubectl run <Pod_Name> --image=<Image_Name>
#by default replica = 1

kubectl exec -it <Pod_Name> -- /bin/bash
# To update index.html file with in the pod
echo Hello nginx! > /usr/share/nginx/html/index.html
apt-get update
# To install curl command with-in the pod
apt-get install curl
# View the details of index.html
curl localhost

# Edit yaml file using nano editor
nano <YAML_File_Name>.yaml
# Create the pod
kubectl create -f <YAML_File_Name>.yaml
# To describe a pod
kubectl describe <Pod_Name>
# To view all the deployment objects
kubectl get deployments
# To edit and make changes using nano editor
KUBE_EDITOR="nano" kubectl edit deployment <Deployment_Name>
# To edit the replicas to scale the pods
kubectl scale deployments <Deployment_Name> --replicas=3

# To watch the activites of the pod
kubectl get pod <Pod_Name> --watch
# To get the process Id of the pod
ps aux
# To kill the process
kill <Process_ID>
# To vget the list of storage units
gcloud compute disks list
# Convert to encode format
echo -n 'my-app' | base64
# Create configMaps from files
kubectl create configmaps <configMap Name> -from-file=file.txt -from-file=file2.txt

# Few notes
GKE: Google Kubernetes Engine
Infra on GCE Virtual machines
GCE: Google Compute Engine (IaaS)

using kubectl

Hybrid = On-prem + Public Cloud
	On-premise: bare metal or VMs
	Legacy infra, large on-prem datacenters
	Medium-term importance
Multi-Cloud
	More than 1 public cloud provider
	
IaaS
AWS Elastic Compute Cloud (EC2)
GCP Compute Engine (GCE)

PaaS
AWS Elastic Beanstalk
GCP App Engine

Volume:
awsElasticBlockStore
gcePersistentDisk

Kube Control (kubectl)

kubefed -> Administer federated clusters
Federated Cluster -> group of multiple clusters (multiple-cloud or hybrid)

Imperativec commands (No .yaml or config files)
kubectl run ...
kubectl expose ...
kubectl autoscale ...

Imperative Object Configuration (kubectl + yaml or config files used)
kubectl create -f config.yaml
kubectl replace -f config.yaml
kubectl delete -f config.yaml

Declarative Object Configuration (Only .yaml or config files used)
kubectl apply -f config.yaml

# env variable as a key-value pair in a configmap
kubectl create configmap <ConfigMap_Name> --from-literal=special.how=very


