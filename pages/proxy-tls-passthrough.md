---
tags: [traefik, nginx, proxy, tls, passthrough]
icon: ":construction_worker:"
---


# Traefik Proxy

```yaml
# traefik.yaml

entryPoints:
  unsecure:
    address: :80
    http:
      redirections:
        entryPoint:
          to: secure
          scheme: https
  secure:
    address: :443

providers:
  file:
    filename: haze.yaml
    watch: true
```

```yaml
# haze.yaml
tcp:
  routers:
    haze_router:
      entryPoints:
        - secure
      rule: "HostSNI(`haze.ibp.local`)"
      service: haze_backend
      tls:
        passthrough: true

  services:
    haze_backend:
      loadBalancer:
        servers:
          - address: "127.0.0.1:8081"
```

# Nginx

TLS passthrough passes request directly to provided endpoint without terminating TLS

```text
stream {
  map $ssl_preread_server_name $name {
    silent-pine.harsh.cloud backend2;
    default https_default_backend;
  }

  upstream backend2 {
    server xxx.xxx.xxx.xxx:443;
  }

  upstream https_default_backend {
    server 127.0.0.1:443;
  }

  server {
    # proxy_protocol on; 
    listen 443;
    proxy_pass $name;
    ssl_preread on;
  }
}
```

#### Reference
- https://stackoverflow.com/questions/34741571/nginx-tcp-forwarding-based-on-hostname/40135151#40135151

!!! Note
server will be proxy only don't try to setup website/proxy_pass etc on gateway nginx it will create conflict since both will try to listen 443 AFAIK
!!!
