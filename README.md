Basic Django and Kubernetes setup for local deployment.

Requires minikube and skaffold:

https://skaffold.dev/docs/quickstart/

## Create images

```bash
minikube start --profile custom
skaffold config set --global local-cluster true
eval $(minikube -p custom docker-env)
```

## Create pods

```bash
skaffold dev --port-forward
```

## Set up database

First run `kubectl get pods` to find the name of the **django** pod.

e.g.

```bash
kubectl exec django-6f94c5dfcf-vmxgz -it -- ./manage.py migrate
kubectl exec django-6f94c5dfcf-vmxgz -it -- ./manage.py createsuperuser
```

