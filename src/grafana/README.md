## Deployment on kubernetes with helm

Add Grafana helm repo
```
helm repo add grafana \
  https://grafana.github.io/helm-charts

helm repo update
```
then install grafana:
```
helm upgrade --install \
  grafana grafana/grafana \
  --namespace grafana \
  --create-namespace \
  --values grafana-values.yaml \
  --wait
```

After the deployment get the password with:
```
kubectl --namespace grafana \
  get secret grafana \
  --output jsonpath="{.data.admin-password}" \
  | base64 --decode ; echo
```

```
kubectl port-forward -n grafana grafana-[xyz] 8080:80
```