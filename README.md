# Kubernetes Monitoring Stack manifest files

## How To Use

### Create Namespace

```bash
kubectl create namespace monitoring
```

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

### Kube State Metrics

```bash
kubectl apply -f kube-state-metrics/
```

### Loki

```bash
kubectl apply -f loki/
```

You can customize loki.yaml secret by editing loki.config, then encode it to base64 and insert it to loki-secret.yaml

```bash
cat loki.config | base64
```

## Destroy

To destroy everything at once, use

```bash
kubectl delete -f alertmanager/ grafana/ kube-state-metrics/ loki/ node-exporter/ prometheus/
```

## Using PersistentVolume / EmptyDir

If you want to use PersistentVolume, change the volume section in grafana-deployment.yaml and prometheus-deployment.yaml to PersistentVolume and comment out emptyDir, then re-deploy with prometheus-volume.yaml and grafana-volume.yaml