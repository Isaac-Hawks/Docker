# Download:
```bash
git clone https://github.com/Isaac-Hawks/jellyfin &&
cd jellyfin
```
# Setup/Deployment
For this to work, you need docker + docker-compose on your device that will be hosting your Jellyfin server.

If you do not already have these installed, run this command:  

```bash
sudo apt-get update && sudo apt-get install docker.io docker-compose -y

```

After you have docker installed, you have to start the container in the jellyfin directory:  
``` sudo docker-compose up -d ``` 
Note: If this is your first time doing this, docker will need to download the jellyfin image.


If you are accessing your server from your host machine, then you will need to navigate to http://127.0.0.1:8096.  
If you are accessing it from a different device, then you will need to navigate to http://server-ip:8096.
