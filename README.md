# Kubernetes Monitoring Stack manifest files

## How To Use

### Prometheus

```bash
kubectl apply -f prometheus/
```

### Grafana

```bash
kubectl apply -f grafana/
```

### Alert Manager

```bash
kubectl apply -f alertmanager/
```

### Node-Exporter

```bash
kubectl apply -f node-exporter/
```

### kube-state-metrics

```bash
kubectl apply -f kube-state-metrics/
```
