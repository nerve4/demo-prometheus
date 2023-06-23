## Deployment on kubernetes with helm

Make sure grafana repo is on:
```
helm repo add grafana \
  https://grafana.github.io/helm-charts

helm repo update
```

then install loki:
```
helm upgrade --install \
  loki grafana/loki-stack \
  --namespace grafana \
  --create-namespace \
  --wait
```

