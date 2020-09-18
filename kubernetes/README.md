## Set up a cluster to get started

#### 1. Install nginx ingress

Initialize your user as a cluster-admin with the following command: 
`kubectl create clusterrolebinding cluster-admin-binding \
  --clusterrole cluster-admin \
  --user $(gcloud config get-value account)
`

Deploy ingress

`kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/controller-v0.35.0/deploy/static/provider/cloud/deploy.yaml
`

#### 2. Install cert-manager

Add repo helm-chart

`helm repo add jetstack https://charts.jetstack.io`

and create a namespace for cert-manager

`kubectl create namespace cert-manager`

thereafter apply cert-manager.crds

`kubectl apply --validate=false -f https://github.com/jetstack/cert-manager/releases/download/v0.14.1/cert-manager.crds.yaml`

later apply ClusterIssuer

`kubectl apply -f ssl/cert-manager.yml`

and at the end install helm-chart for cert-manager

`helm install cert-manager --namespace cert-manager jetstack/cert-manager --version v0.14.1`

#### 3. Install jenkins

`helm install jenkins stable/jenkins -f jenkins/values.yaml`

#### 4. Install Prometheus Operator

To install the namespace. 

`kubectl create namespace monitoring`

installation prometheus, writing comand.

`helm install prometheus-operator -f Prometheus\ Operator/values.yaml stable/prometheus-operator  --namespace monitoring`