# Azure Secure Web Server V1 Deployment

## Update Ubuntu

```bash
sudo apt update
sudo apt upgrade -y
```

## Install Nginx

```bash
sudo apt install nginx -y
```

## Enable Nginx

```bash
sudo systemctl enable nginx
sudo systemctl start nginx
```

## Upload Website

scp ...

## Replace Default Page

sudo cp ~/index.html /var/www/html/index.html

## Reload Nginx

sudo systemctl reload nginx
```