# mediastack

MediaStack

# Introduction

This repository is dedicated to the docker-compose.yml that allows for an automated media server, that can process requests for movies or tv-shows, including anime and newer movies. This docker-compose file should not be used for piracy and the creators and contributors of this repository do not condone piracy. The repository focuses on using qBittorrent and a indexer manager called Prowlarr, to handle requests from Overseerr, a manager that handles requests to your library. Prowlarr passes requests onto two different indexer managers, Sonarr and Radarr. These docker images have their own documentation that can be found from [Trash-Guides](https://trash-guides.info/) . Prowlarr, Sonarr, Radarr and qBittorrent are all behind a Gluetun VPN container. While it is unclear whether it is necessary that Radarr and Sonarr should be behind a VPN, I put the container behind the VPN to make sure content can be accessed without being blocked from ISPs. The VPN container provider used in the example is AirVPN, which allows port-forwarding to multiple locations around the world. All of the automatically downloaded media is watched on a Plex Media Server run in a docker container, but it can also be run on bare-metal. The media and torrent files are hardlinked to reduce the rewriting and copying of files, and instead allowing files to be linked to different files, instead of copying files over. For further information of 

- **File Structure**
	
	- Below is the file structure of the media and torrent files. The containers are given access to different files all underneath the data folder to utilise hardlinking and file linking to reduce the impact of downloading large files.
	
	- ``mediastack
		- ``config
			- ``qbittorrent
			- ``prowlarr
			- ``sonarr
			- ``radarr
			- ``overseerr
			- ``plex
		- ``data
			- ``torrents
				- ``movies
				- ``tv
			- ``media
				- ``movies
				- ``tv

