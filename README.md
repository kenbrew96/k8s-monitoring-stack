## PROJECT 5: Kubernetes Monitoring with Prometheus & Grafana

### 📁 GitHub Structure
```
k8s-monitoring-stack/
├── prometheus-values.yaml
├── grafana-values.yaml
```

### 📄 `prometheus-values.yaml`
```yaml
alertmanager:
  enabled: true
server:
  global:
    scrape_interval: 15s
  persistentVolume:
    enabled: false
```
**Explanation**: Enables Prometheus Alertmanager and customizes the global scrape interval.

### 📄 `grafana-values.yaml`
```yaml
ingress:
  enabled: true
  annotations:
    nginx.ingress.kubernetes.io/rewrite-target: /
  hosts:
    - grafana.example.com
adminUser: admin
adminPassword: admin
```
**Explanation**: Enables ingress and sets up Grafana admin credentials.

### 📄 Helm Install Command
```sh
helm repo add prometheus-community https://prometheus-community.github.io/helm-charts
helm install monitor prometheus-community/kube-prometheus-stack -f prometheus-values.yaml -f grafana-values.yaml
```
**Explanation**: Installs monitoring tools using Helm and custom values files.
