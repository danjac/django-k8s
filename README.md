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

## View in browser

1. Run `minikube ip` and make a note of the IP address.
2. In _/etc/hosts/_ add line `192.168.49.2    minikube.local`.
3. Open browser at _https://minikube.local_.

