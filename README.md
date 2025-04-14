### 📄 Helm Install Command
```sh
helm repo add prometheus-community https://prometheus-community.github.io/helm-charts
helm install monitor prometheus-community/kube-prometheus-stack -f prometheus-values.yaml -f grafana-values.yaml
```
**Explanation**: Installs monitoring tools using Helm and custom values files.
