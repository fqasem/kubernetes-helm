# kubernetes-helm
Project showing how to create and use Kubernetes helm charts.



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

