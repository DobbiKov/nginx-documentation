# Documentation | Config

In `/etc/nginx/sites-available/`
Write to mern.dobbikov.ga.conf:
```
server{
    listen 80;
    listen [::]:80;

    server_name mernapi.dobbikov.ga;
    location / {
        proxy_pass http://45.67.56.85:8080;
    }
}
```