## Erorr
Fix SharedArrayBuffer error ffmpeg

## For Nginx
Edit your Nginx config (/etc/nginx/sites-available/default):

```
nginxCopyEditserver {
    listen 80;
    server_name yourdomain.com;
    location / {
        add_header Cross-Origin-Opener-Policy same-origin;
        add_header Cross-Origin-Embedder-Policy require-corp;
    }
}
```
Then restart Nginx:

sudo systemctl restart nginx

## For Apache

Edit .htaccess or Apache config:

apache
```
<IfModule mod_headers.c>
    Header set Cross-Origin-Opener-Policy "same-origin"
    Header set Cross-Origin-Embedder-Policy "require-corp"
</IfModule>
```
Then restart Apache:


sudo systemctl restart apache2
