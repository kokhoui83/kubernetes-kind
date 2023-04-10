# Foo Bar App
Example applications to test nginx ingress setup for kind

- Ensure ingress-nginx is already setup
- Setup
```
kind apply -f foo-bar-app/deployment.yaml
```
- Test
```
# should output "foo-app"
curl localhost/foo/hostname
# should output "bar-app"
curl localhost/bar/hostname
```
- Reference
https://kind.sigs.k8s.io/docs/user/ingress/