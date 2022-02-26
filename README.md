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
skaffold dev
```

## View in browser

1. Run `minikube ip` and make a note of the IP address.
2. In _/etc/hosts/_ add line `192.168.49.2    minikube.local`.
3. Open browser at _https://minikube.local_.

