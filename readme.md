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


## Link

```
<script src="https://cdn.jsdelivr.net/gh/tranchausky/ffmpeg-js-cnd@main/ffmpeg.min.js"></script>
<script type="module">

const { createFFmpeg } = FFmpeg;

const ffmpeg = createFFmpeg({ log: true, corePath: 'https://cdn.statically.io/gh/tranchausky/ffmpeg-js-cnd@main/ffmpeg-core.js' });

</script>

```