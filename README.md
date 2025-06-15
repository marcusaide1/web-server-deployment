![landing page](https://github.com/user-attachments/assets/a7e188dd-3814-49be-a094-82cd5f6b9075)
Cloud Provider:** AWS (EC2 Ubuntu 22.04)
Web Server:** Nginx
Domain:** Namecheap domain (`marcusaide.online`)
SSL:** Let's Encrypt with Certbot
1. ✅ Provision the Ubuntu Server (EC2)

- Launched an EC2 instance (Ubuntu 22.04) on AWS
- Opened ports **80 (HTTP)** and **443 (HTTPS)** in the security group
- SSH'd into the server:
  ```bash
  ssh -i "my-key.pem" ubuntu@34.245.58.6
2. ✅ Install and Configure Nginx
   sudo systemctl start nginx
   sudo apt update && sudo apt install nginx -y
   verfied that its working
   http://34.245.58.6

   npm init -y
npm install express

   npm install pm2 -g
pm2 start server.js
pm2 startup
4. ✅ Connected Domain from NameCheap to server
   Pointed domain marcusaide.online and www.marcusaide.online to EC2's public IP using A records in Namecheap's DNS panel.

5. ✅Prepared Static Landing Page
   Created Mkdir Public and Created File html.index.
6. ✅Ensured Nginx serve is by editing the config
   sudo nano /etc/nginx/sites-available/default
7. ✅Next
   sudo nginx -t && sudo systemctl reload nginx
8. ✅Secure with ssh (certbot)
   sudo apt install certbot python3-certbot-nginx -y
   sudo certbot --nginx -d marcusaide.online -d www.marcusaide.online
9. ✅Verify Https
   curl -I https://marcusaide.online
