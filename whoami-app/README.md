# Simple whoami Application
Application to test `traefik` setup

- Setup
```
kubectl apply -f deployment.yaml
```

- Test
```
curl http://192.168.50.38/

Hostname: whoami-6d97bf7dcb-p7d7w
IP: 127.0.0.1
IP: ::1
IP: 10.42.1.4
IP: fe80::6415:b5ff:fe13:f6e9
RemoteAddr: 10.42.0.7:44064
GET / HTTP/1.1
Host: 192.168.50.38
User-Agent: curl/7.68.0
Accept: */*
Accept-Encoding: gzip
X-Forwarded-For: 10.42.1.0
X-Forwarded-Host: 192.168.50.38
X-Forwarded-Port: 80
X-Forwarded-Proto: http
X-Forwarded-Server: traefik-56b8c5fb5c-mfrhz
X-Real-Ip: 10.42.1.0
```