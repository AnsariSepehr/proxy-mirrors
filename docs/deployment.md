# Deployment Guide — Son Proxy Mirrors

This guide explains how to deploy the **Son Proxy Mirrors** website on a Linux server using Nginx.

## Prerequisites

- Linux server (Ubuntu/Debian recommended)
- Nginx installed
- Domain name pointed to the server (e.g., `nexus.son.ir`)
- Root or sudo access
- (Recommended) SSL certificate via Let's Encrypt

## Step-by-Step Deployment

### Part 1: Create the Web Directory

```bash
sudo mkdir -p /var/www/mirrors
sudo chown -R $USER:www-data /var/www/mirrors

### Part 2: Upload the File
- Place your index.html in:

```text
/var/www/mirrors/index.html

### Part 3: Configure Nginx
- Create the site configuration:

```bash
sudo nano /etc/nginx/sites-available/mirrors

- Paste this (replace nexus.son.ir with your domain):

```nginx
server {
    listen 80;
    server_name nexus.son.ir;

    root /var/www/mirrors;
    index index.html;

    location /mirrors/ {
        try_files $uri $uri/ =404;
        add_header Cache-Control "no-cache, no-store, must-revalidate";
    }

    # Redirect HTTP to HTTPS
    return 301 https://$host$request_uri;
}
server {
    listen 443 ssl http2;
    server_name nexus.son.ir;
    ssl_certificate /etc/letsencrypt/live/nexus.son.ir/fullchain.pem;
    ssl_certificate_key /etc/letsencrypt/live/nexus.son.ir/privkey.pem;
    root /var/www/mirrors;
    index index.html;
    location /mirrors/ {
        try_files $uri $uri/ =404;
    }
}

### Part 4: Enable the Site
```bash
sudo ln -s /etc/nginx/sites-available/mirrors /etc/nginx/sites-enabled/
sudo nginx -t                    # Test config
sudo systemctl reload nginx      # Apply changes

### Part 5: (Recommended) Install SSL with Certbot
```bash
sudo apt update
sudo apt install certbot python3-certbot-nginx
sudo certbot --nginx -d nexus.son.ir

- Follow the prompts to enable HTTPS.

### Part 6: Verify
- Visit: https://nexus.son.ir/mirrors/

- Updating the Site
- To update the website:

- Edit /var/www/mirrors/index.html

- Reload Nginx:

```bash
sudo systemctl reload nginx

### Adding New Mirrors
Edit the mirrors object in the JavaScript section of index.html and add new cards in the HTML.
