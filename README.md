Basic Django and Kubernetes setup for local deployment.

## Create images

```bash
minikube start
minikube addons enable ingress
minikube build . -t django-webapp
```

## Create pods

```bash
kubectl apply -f ./k8s/postgres
kubectl apply -f ./k8s/django
kubectl apply -f ./k8s/ingress.yaml

kubectl get deployments
kubectl get pods
kubectl get services
kubectl get ingress
```

