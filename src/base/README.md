## Deployment on kubernetes with helm

```
helm repo add prometheus \
  https://prometheus-community.github.io/helm-charts

helm repo update
```

then install:
```
helm upgrade --install \
  prometheus prometheus/prometheus \
  --namespace prometheus \
  --create-namespace \
  --wait
```

```
kubectl port-forward -n prometheus prometheus-server-[xyz] 9090:9090
```