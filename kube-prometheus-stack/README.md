# Kubebernetes Prometheus Stack

## Setup
- Create namespace
```
kubectl create namespace monitoring
```

## Install via helm
```
helm install --namespace monitoring kube-prometheus prometheus-community/kube-prometheus-stack
```

## Access Grafana
- Check services
```
kubectl --namespace monitoring get services
NAME                                       TYPE        CLUSTER-IP      EXTERNAL-IP   PORT(S)                      AGE
alertmanager-operated                      ClusterIP   None            <none>        9093/TCP,9094/TCP,9094/UDP   24m
kube-prometheus-grafana                    ClusterIP   10.96.138.109   <none>        80/TCP                       26m
kube-prometheus-kube-prome-alertmanager    ClusterIP   10.96.251.150   <none>        9093/TCP                     26m
kube-prometheus-kube-prome-operator        ClusterIP   10.96.7.183     <none>        443/TCP                      26m
kube-prometheus-kube-prome-prometheus      ClusterIP   10.96.46.227    <none>        9090/TCP                     26m
kube-prometheus-kube-state-metrics         ClusterIP   10.96.251.115   <none>        8080/TCP                     26m
kube-prometheus-prometheus-node-exporter   ClusterIP   10.96.195.29    <none>        9100/TCP                     26m
prometheus-operated                        ClusterIP   None            <none>        9090/TCP                     24m
```

- Port-forwarding
```
kubectl --namespace monitoring port-forward svc/kube-prometheus-grafana 3000:80
```

- Get password (user is `admin`)
```
kubectl --namespace monitoring get secret kube-prometheus-grafana -o jsonpath="{.data.admin-password}" | base64 --decode ; echo
```