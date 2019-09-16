This is a helm chart repository to deploy `nginx` docker container on k8s.

## Installing Help

We will run tiller locally as it's more secure in production environment.

```
# install helm cli 
curl -L https://git.io/get_helm.sh | bash

# create 'tiller' namespace
kubectl create namespace tiller

# open a new terminal and run tiller client mode
export TILLER_NAMESPACE=tiller
tiller -listen=localhost:44134 -storage=secret -logtostderr

# open a new terminal
export HELM_HOST=:44134

helm init --client-only
```

## Deploying

```
git clone https://github.com/narayanprusty/HTTPBin-EKS-Helm.git && cd HTTPBin-EKS-Helm
helm install ./
```