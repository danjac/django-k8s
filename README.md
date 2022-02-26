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

