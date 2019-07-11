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

