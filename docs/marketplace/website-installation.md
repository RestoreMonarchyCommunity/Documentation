### Requirements
Before installing Marketplace, you should check that your web server has the following requirements for Marketplace Website to work.

* .NET Core Runtime >= 3.1
* MySQL Server >= 5.7 OR SQL Server 2017

Marketplace website is running on ASP.NET Core 3.1 with Blazor WebAssembly. It may also require some other packages in order to work, depending on OS.

### Installing Web
**Installing .NET Core Runtime**  
1. Firstly register Microsoft key and feed
```
wget -q https://packages.microsoft.com/config/ubuntu/18.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```
2. Then install the ASP.NET Core 3.1 Runtime
```
sudo add-apt-repository universe
sudo apt-get update
sudo apt-get install apt-transport-https
sudo apt-get update
sudo apt-get install aspnetcore-runtime-3.1
```
**Downloading and installing Marketplace-Web**   
1. Download latest release from Marketplace-Web repo on Github [here](https://github.com/RestoreMonarchy/Marketplace-Web/releases)
2. Upload `Marketplace.zip` to your server via some FTP Client (e.g. FileZilla) to `/var/www/marketplace-web` directory
3. On your SSH client use `cd /var/www/marketplace-web` and then type in `unzip Marketplace.zip` to extract the zip file

**Setting up Nginx Web Server**
1. Create a new `marketplace-web.conf` file inside `/etc/nginx/sites-available`
2. Open it and paste the following text, remember to change `DOMAINNAME.COM` variable to your domain address. 

```conf
server {
    listen 80;
    server_name DOMAINNAME.COM;
    return 301 https://$server_name$request_uri;
}

server {
    listen 443 ssl http2;
    server_name DOMAINNAME.COM;

    root /var/www/marketplace-web/web;

    access_log /var/www/marketplace-web/logs/servers.app-access.log;
    error_log  /var/www/marketplace-web/logs/servers.app-error.log error;

    # SSL Configuration
    ssl_certificate /etc/letsencrypt/live/DOMAINNAME.COM/fullchain.pem;
    ssl_certificate_key /etc/letsencrypt/live/DOMAINNAME.COM/privkey.pem;
    ssl_session_cache shared:SSL:10m;
    ssl_protocols TLSv1.2;
    ssl_ciphers 'ECDHE-ECDSA-AES256-GCM-SHA384:ECDHE-RSA-AES256-GCM-SHA384:ECDHE-ECDSA-CHACHA20-POLY1305:ECDHE-RSA-CHACHA20-POLY1305:ECDHE-ECDSA-AES128-GCM-SHA256:ECDHE-RSA-AES128-GCM-SHA256:ECDHE-ECDSA-AES256-SHA384:ECDHE-RSA-AES256-SHA384:ECDHE-ECDSA-AES128-SHA256:ECDHE-RSA-AES128-SHA256';
    ssl_prefer_server_ciphers on;

    location / {
        proxy_pass http://localhost:5046;
        proxy_http_version 1.1;
        proxy_set_header Upgrade $http_upgrade;
        proxy_set_header Connection keep-alive;
        proxy_set_header Host $host;
        proxy_cache_bypass $http_upgrade;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header X-Forwarded-Proto $scheme;
    }
}
```
3. Now to add your site to Nginx enabled sites use
```
sudo ln -s /etc/nginx/sites-available/marketplace-web.conf /etc/nginx/sites-enabled/marketplace-web.conf
```
4. You then have to create SSL certificate, learn more about how to do it [here](https://pterodactyl.io/tutorials/creating_ssl_certificates.html#method-1-using-certbot)
5. And finally restart your Nginx web server via
```
systemctl restart nginx
```

**Running Marketplace-Web**
1. First you should make sure your Marketplace-Web is working properly, so go to web files directory and use start the website.
```
cd /var/www/marketplace-web/web
dotnet Marketplace.Server
```
!!! note Remember to first properly configure the website in `appsettings.json` before running!

2. Now stop the website running by pressing `ctrl + c` because we want to have it running as service.

3. To run a service first you have to create service definition file
```
sudo nano /etc/systemd/system/marketplace-web.service
```
4. When nano file opens paste in the text below and then save the file
```service
[Unit]
Description=ASP.NET Core Marketplace Web

[Service]
WorkingDirectory=/var/www/marketplace-web/web
ExecStart=/usr/bin/dotnet /var/www/marketplace-web/web/Marketplace.Server.dll
Restart=always
# Restart service after 10 seconds if the dotnet service crashes:
RestartSec=10
KillSignal=SIGINT
SyslogIdentifier=marketplace-web
User=www-data
Environment=ASPNETCORE_ENVIRONMENT=Production
Environment=DOTNET_PRINT_TELEMETRY_MESSAGE=false

[Install]
WantedBy=multi-user.target
``` 
5. Now to enable the service execute following:
```
sudo systemctl enable marketplace-web.service
```
6. And so now run the service and see the status
```
sudo systemctl start marketplace-web.service
sudo systemctl status marketlace-web.service
```
