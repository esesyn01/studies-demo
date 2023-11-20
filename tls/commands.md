```
docker run --name some-nginx -p 8080:8080 -d nginx
```

```
nano /etc/nginx/conf.d/nginx.conf

zmienić port z 80 na 8080

nginx -s reload
```

```
apt update
apt install libnss3-tools wget
wget https://github.com/FiloSottile/mkcert/releases/download/v1.4.3/mkcert-v1.4.3-linux-amd64
chmod +x mkcert-v1.4.3-linux-amd64
mv mkcert-v1.4.3-linux-amd64 /usr/local/bin/mkcert
```

```
mkcert -install
mkcert localhost
```

```
nano /etc/nginx/conf.d/nginx.conf

listen 8080 ssl;
ssl_certificate /ścieżka/do/localhost.pem;
ssl_certificate_key /ścieżka/do/localhost-key.pem;


nginx -s reload
```
