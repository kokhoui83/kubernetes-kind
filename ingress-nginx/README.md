# Ingress Nginx for Kind
- Requires the `extraPortMappings` and `node-labels` to work
- Step 1
```
kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/main/deploy/static/provider/kind/deploy.yaml
```
- Step 2
```
kubectl wait --namespace ingress-nginx \
  --for=condition=ready pod \
  --selector=app.kubernetes.io/component=controller \
  --timeout=90s
```
- Reference
https://kind.sigs.k8s.io/docs/user/ingress/