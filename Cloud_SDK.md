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
