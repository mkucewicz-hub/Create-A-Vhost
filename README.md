# Create-A-Vhost!
 Simple script that will deploy a virtual host on ubuntu


## Instructions
Start of with adding a new A record for the host at your host provider.
In your server (ubuntu) 

```bash
use git clone https://github.com/xhika/deployVH.git
```

### Terminal
```bash
cd into folder

chmod +w+r+x install.sh
chmod +w+r+x config.sh

!! Before running the script make sure to 
edit the NGINX_HOST value to your desired host name !!

sudo ./install.sh
```

### Multiple Virtual Hosts
If multiple host wants to be created, don't forget to change the NGINX_HOST variable's value in .env file for a new Virtual Host to be created and then run 
``` bash sudo ./config```


## AWS (EC2)
For this script to work on AWS EC2 instance follow these steps:
```
1. Enter EC2 dashboard -> Instances 
2. Click on your newly created instance and a window will open below.
3. Click Security tab, then inder Security group click on link 
4. Edit inbound rules and add rules for http & https 
select source to be 0.0.0.0/0 
as the first ssh is on default.
5. Save rules!
```

## Troubleshooting
- If any troubles occur, make sure ports 80,443 are available.
- If certbot fails, make sure envsubst have replaced variables correctly check in /etc/nginx/sites-enabled/{your_host_name}

