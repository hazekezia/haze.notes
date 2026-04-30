---
icon: linux
description: This tutorial about using NGINX reverse proxy.
---

# NGINX: Reverse Proxy

**NGINX Installation**

```bash
sudo apt update
sudo apt install nginx -y
```

Check for NGINX status

```bash
sudo systemctl status nginx
```

**NGINX Configuration**

Create configuration files on /etc/nginx/sites-available/. Change **`example.com`** to your domain.

```bash
sudo nano /etc/nginx/sites-available/example.com
```

Add this configurations. Change `example.com` and `http://localhost:3000` to your use port.

```bash
server {
    listen 80;
    server_name example.com www.example.com;

    location / {
        proxy_pass http://localhost:3000;
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header X-Forwarded-Proto $scheme;
    }
}
```

Activate this using symlink to sites-enabled directory.

```bash
sudo ln -s /etc/nginx/sites-available/example.com /etc/nginx/sites-enabled/
```

Last, check if conf OK then reload NGINX.

```bash
sudo nginx -t
sudo systemctl reload nginx
```
