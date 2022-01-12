# Introduction
This is a docker stack which contains Plex, xteve and a little service to resatrt the streaming service of a vbox.

All the containers will be using their own network so thex are accessable via hostnames, only xteve is benefiting from this tho as it can be easily added to plex that way.

# Environment Variables
Set these variables for your stack to work. Im using Portainer where I can simply add them in a webgui. Can also be a .env file or something.

- `VBOX_USERNAME` the username required to the login the vbox web gui
- `VBOX_PASSWORD` the password requiered to the login to vbox web gui
- `VBOX_IP` the ip of the vbox
- `VBOX_SLEEPTIME` how often the service should check the status to start the streamer service again
- `XTEVE_PORT` port for xteve
- `XTEVE_CONFIG_PATH` where the xteve config should be mapped to on the host
- `PLEX_MAX_LOG_SIZE` max log size e.g. `1m`
- `PLEX_PUID userid` for plex
- `PLEX_PGID groupid` for plex
- `PLEX_CONFIG_PATH` where the plex config should be mapped to on the host
- `PLEX_MEDIA_PATH` where your media is on the host for plex 
- `PLEX_HW_DEVICE` a device plex can use for hw transcoding. e.g. `/dev/dri:/dev/dri`
- `PLEX_ADVERTISE_IP` which ip plex should advertise as server, use the same as the host running plex


# Fixes
## Plex indirect connection
- go to your plex server's setting <img src="https://user-images.githubusercontent.com/24566692/149229186-b1cd51db-1139-4ae9-8ed9-c03842705af8.png" width="30"> -> `Preferences` -> `Network`.
- For `LAN Networks` enter your lan network e.g `192.168.1.0/24`
- For `Own URLs for accessing this server` enter `http://<your-hosts-ip>:<port>`. 
 
For the ip adress use the same as for `PLEX_ADVERTISE_IP`.
Plex's default port is 32400
