# Kubernetes Dashboard

## Setup
- Install
```
kubectl apply -f dashboard.yaml
```
- Create admin account
```
kubectl apply -f admin-user.yaml
```

## Login
- Check service
```
kubectl --namespace kubernetes-dashboard get service
NAME                        TYPE        CLUSTER-IP      EXTERNAL-IP   PORT(S)    AGE
dashboard-metrics-scraper   ClusterIP   10.96.108.173   <none>        8000/TCP   51m
kubernetes-dashboard        ClusterIP   10.96.152.102   <none>        443/TCP    51m
```
- Port-forwarding
```
kubectl -n kubernetes-dashboard port-forward svc/kubernetes-dashboard 8001:8000
```
- Create token
```
kubectl -n kubernetes-dashboard create token admin-user
```
- Open browser
```
http://localhost:8001/api/v1/namespaces/kubernetes-dashboard/services/https:kubernetes-dashboard:/proxy/
http://localhost:8001/api/v1/namespaces/kubernetes-dashboard/services/https:kubernetes-dashboard:/proxy/#/login
```