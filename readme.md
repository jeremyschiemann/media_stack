# Fixes
## Plex indirect connection
- go to your plex server's setting <img src="https://user-images.githubusercontent.com/24566692/149229186-b1cd51db-1139-4ae9-8ed9-c03842705af8.png" width="30"> -> `Preferences` -> `Network`.
- For `LAN Networks` enter your lan network e.g `192.168.1.0/24`
- For `Own URLs for accessing this server` enter `http://<your-hosts-ip>:<port>`. 
 
For the ip adress use the same as for `PLEX_ADVERTISE_IP`.
Plex's default port is 32400
