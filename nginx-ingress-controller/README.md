# NGINX Ingress Controller

## Install
- Apply deployment file
```
kubectl apply -f deployment.yaml
```
- Check
```
kubectl wait --namespace ingress-nginx \
  --for=condition=ready pod \
  --selector=app.kubernetes.io/component=controller \
  --timeout=90s
```

## Uninstall
```
kubectl delete -f deployment.yaml
```

## Reference
- https://kind.sigs.k8s.io/docs/user/ingress/
- https://kubernetes.github.io/ingress-nginx/deploy/
