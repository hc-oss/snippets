---
tags: [go-cd, nginx]
icon: ":construction_worker:"
---

# GoCD

### Nginx Configuration

```text
location /go {
    proxy_pass              http://localhost:8153;
    proxy_set_header        Host $host;
    proxy_set_header        X-Real-IP $remote_addr;
    proxy_set_header        X-Forwarded-For $proxy_add_x_forwarded_for;
    proxy_set_header        X-Forwarded-Proto $scheme;
    proxy_connect_timeout   150;
    proxy_send_timeout      100;
    proxy_read_timeout      100;
    proxy_buffers           4 32k;
    client_max_body_size    8m;
    client_body_buffer_size 128k;
}
```

### Add directory to PATH

```
sudo vi /usr/share/go-agent/wrapper-config/wrapper-properties.conf # edit path variable
```
