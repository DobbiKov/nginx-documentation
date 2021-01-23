# Documentation | Config

In `/etc/nginx/sites-available/`
Write to mern.dobbikov.ga.conf for back-end:
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

Write to mern.dobbikov.ga.conf for front-end:
```
server{
   listen 80;
   listen [::]:80;
   server_name mern.dobbikov.ga www.mern.dobbikov.ga;

   root /var/www/mira;
   location / {
      try_files $uri $uri/ /index.html;
   }
  }
```

Write to scout.dobbikov.ga for front-end with files:
```
server{
   listen 80;
   listen [::]:80;
   server_name scout.dobbikov.ga www.scout.dobbikov.ga;

   root /var/www/scout;
   location / {
      try_files $uri $uri/ /index.html;
   }
   location /assets/img {
      root /var/www/scout;
   }
}
```
