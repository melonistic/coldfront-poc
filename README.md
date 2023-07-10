# coldfront-nerc

## WUSTL-RIS

Install GCloud SDK.

gcloud auth login

gcloud components install kubectl

gcloud components install gke-gcloud-auth-plugin

gcloud config set project <<your-gcp-project>>

gcloud container clusters create coldfront-poc --num-nodes=3 --machine-type=custom-8-16384 --region=us-central1 

gcloud container clusters get-credentials coldfront-poc --region=us-central1

git clone https://github.com/WashU-IT-RIS/coldfront-poc.git

cd coldfront-poc

kubectl apply -k crds/

kubectl apply -k k8s/base/
 
kubectl apply -k k8s/overlays/dev

kubectl get all -n coldfront

kubectl delete all --all -n coldfront

gcloud container clusters delete coldfront-poc --region=us-central1


https://cloud.google.com/sdk/gcloud/reference/container/clusters/create


- Packages [ubccr/coldfront](https://github.com/ubccr/coldfront) and the
[nerc-project/coldfront-plugin-cloud](https://github.com/nerc-project/coldfront-plugin-cloud)
using containers
- Stores the kubernetes base manifests for deployment


