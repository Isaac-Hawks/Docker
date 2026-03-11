# Jellyfin Docker Container
This repository provides a simple Docker-based setup for running a Jellyfin media server.  
It includes a docker-compose configuration and folder structure to make deployment easy.  

## Requirements
- Ubuntu / Debian based systems
- Docker
- Docker Compose
- Internet Connection (for downloading the jellyfin image and metadata)

## Download
```bash
git clone https://github.com/Isaac-Hawks/jellyfin && 
cd jellyfin
```
## Setup/Deployment
For this to work, you need docker + docker-compose on the device that will be hosting your Jellyfin server

If you do not already have them installed, run:
```bash
sudo apt-get update
sudo apt-get install docker.io docker-compose -y

```
After you have docker installed, you have to start the container in the jellyfin directory:
`sudo docker-compose up -d`
Note: If this is your first time doing this, docker will need to download the jellyfin image.

## Container Management
* If you ever want to edit the docker-compose.yml file, run `docker-compose down` from inside the jellyfin directory to remove the container and network,
  then run `docker-compose up -d` to rebuild the container and network
* To temporarily stop the docker container so it doesn't hog all your resources, run `docker stop jellyfin`
  * To start the container again, run `docker start jellyfin`



## Accessing your server
If you are accessing your server from your host machine, then you will need to navigate to http://127.0.0.1:8096.  
Otherwise, if you are accessing your server from a different device, go to http://server-ip:8096
* To find your server ip address, run `hostname -I | awk '{print $1}'` on the machine hosting your Jellyfin server

# Folder Structure
```
/jellyfin
  ├── /cache
  │   └── .gitkeep
  ├── /config
  │   └── .gitkeep
  ├── /media
  │   └── README.md
  ├── docker-compose.yml
  └── README.md
```
## Note:
When you clone this repository, the `cache` and `config` folders will be empty.  
Once you finish the setup process on the webpage, jellyfin will automatically store it's configuration files in the `config` directory.  
When you scan a library for the first time, Jellyfin will download metadata from sources like TVDB/TMDB and store it in the `cache` folder.

# GUI Setup
1. Go to http://127.0.0.1:8096
2. Set your Server name and preferred display language --> next
3. Set a Username and Password --> next
4. If you have any media
   * Click 'Add Media Library'
   * Set Content Type & Library name
   * Select Folders --> /media --> path/to/media, then click Ok
5. Click Ok --> Next
6. Set Language & Country/Region --> Next
7. If you aren't accessing your server from outside your private LAN, then you can uncheck the 'Allow remote connections to this server.' Otherwise keep it checked. Now click Next
8. Click Finish and log back in again
9. Enjoy!

### If you project helped you, consider giving it a ⭐ on GitHub
