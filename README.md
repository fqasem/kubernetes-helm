# kubernetes-helm
Project showing how to create and use Kubernetes helm charts. You will need minikube and helm installed.

**Minikube Guide page:**
https://minikube.sigs.k8s.io/docs/start/?arch=%2Fwindows%2Fx86-64%2Fstable%2Fchocolatey#Service

**Helm Guide Page:**
https://helm.sh/docs/intro/install/

https://helm.sh/docs/intro/quickstart/

https://helm.sh/docs/intro/using_helm/


## Create the helmchart
```
helm create webapp1
```

## Install the first one
```
helm install mywebapp-release webapp1/ --values webapp1/values.yaml
```

## Upgrade after templating
```
helm upgrade mywebapp-release webapp1/ --values mywebapp/values.yaml
```

## Accessing it
```
minikube tunnel
```

## Create dev/prod
```
kubectl create namespace dev
kubectl create namespace prod

helm install my-webapp-dev .\solution\webapp1\ --values .\solution\webapp1\values.yaml -f .\solution\webapp1\values-dev.yaml -n dev

helm install my-webapp-prod .\solution\webapp1\ --values .\solution\webapp1\values.yaml -f .\solution\webapp1\values-prod.yaml -n prod

helm ls --all-namespaces
```

