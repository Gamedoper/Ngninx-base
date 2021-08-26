# Ngninx-base-ssl FREE
Basic Setup with Server / ssl


```
##INSTALL NGINX SSL / AUTO RENEWAL


#Sudo apt install nginx
Sudo apt update
Sudo ufw app list
Sudo ufw allow ’Nginx http’
Sudo ufw status   #if not available # sudo ufw enable
sudo systemctl reload nginx
sudo mkdir -p /var/www/raven_hacks/html
sudo chown -R $USER:$USER /var/www/example.com/html
sudo chmod -R 755 /var/www/raven_hacks
nano /var/www/raven_hacks/html/index.htm
Create sample index html l
sudo nano /etc/nginx/sites-available/raven_hacks
sudo ln -s /etc/nginx/sites-available/raven_hacks/etc/nginx/sites-enabled/
sudo nano /etc/nginx/nginx.conf
sudo nano /etc/nginx/sites-available/raven_hacks
sudo ln -s /etc/nginx/sites-available/raven_hacks /etc/nginx/sites-enabled/
sudo systemctl restart nginx


apt install snapd
snap install core
snap install --classic certbot
ln -s /snap/bin/certbot /usr/bin/certbot
certbot --nginx 
Installs a certificate for domain example.com

##After that below steps we are going to use wildcard 


certbot --server https://acme-v02.api.letsencrypt.org/directory -d *.anglo-indiancuisine.com -d anglo-indiancuisine.com --manual --preferred-challenges dns-01 certonly

certbot certificates
sudo nano /etc/nginx/sites-enabled/raven_hacks
certbot renew
/usr/bin/certbot renew >> /var/log/letsencrypt/renew.log
crontab -e
30 1 * * * /usr/bin/certbot renew >> /var/log/letsencrypt/renew.log


Server {

Root /var/www/html/raven_hacks/html;
Index index.html index.htm;
        
server_name anglo-indiancuisine.com *.anglo-indiancuisine.com;

        location / {
                try_files $uri $uri/ =404;
        }

    listen [::]:443 ssl ipv6only=on; # managed by Certbot
    listen 443 ssl; # managed by Certbot
    ssl_certificate /etc/letsencrypt/live/anglo-indiancuisine.com/ful>
    ssl_certificate_key /etc/letsencrypt/live/anglo-indiancuisine.com>
    include /etc/letsencrypt/options-ssl-nginx.conf; # managed by Cer>
    ssl_dhparam /etc/letsencrypt/ssl-dhparams.pem; # managed by Certb>

}

server {
        listen 80;
        server_name anglo-indiancuisine.com *.anglo-indiancuisine.com;
        return 301 https://$host$request_uri;

}


```


