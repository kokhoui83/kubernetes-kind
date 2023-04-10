# Nginx Web Server
Setup simple nginx cluster in kind cluster
- Requires `ingress-nginx` setup
- Update `/etc/hosts` with the following entry
```
17.0.0.1    localk8s.com
```
- Deploy
```
kubectl apply -f nginx-web-server/deployment.yaml
```
- Test
```
curl localk8s.com/nginx
```