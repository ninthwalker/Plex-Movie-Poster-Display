# Plex Movie Poster Display
Scraps the Plex sessions page to display the current playing movie or TV show poster on a screen.

Disclaimer – I am a network engineer not a programmer. I play around with code. I am publishing this to give back to the communities that has helped me learn. There may be better ways of scraping the Plex Posters, but this is the way I chose to do it. I am open to suggestions. Use at your own risk..

I decided to rewrite the program in PHP and make it browser based. This allows me to have the Raspberry Pi boot to the desktop, automatically start a browser in kiosk mode, and open the PHP site.

This script scraps http://IP_ADDRESS_OF_PLEX_SERVER>:32400/status/sessions for clients and displays the poster of the currently playing movie or TV show. If nothing is currently playing it will pull a random poster of an unwatched movie.

## My Setup
Plex Media Server is running on a dedicated server.
Plex Movie Poster Display is running on separate Raspberry Pi 3 connected to a screen via HDMI. On boot up the Pi launches Chromium in kiosk mode and loads the Plex Movie Poster Display URL.

## Prerequisites
 - A functioning Plex Server
 - Web Server – I am running NGINX
 - PHP – I am running version  5.6.22
 - Your X-Plex-Token. https://support.plex.tv/hc/en-us/articles/204059436-Finding-your-account-token-X-Plex-Token

## Features 
- Custom Text on top and bottom of posters.
- Cache posters locally.
- Custom Image
- Web Frontend for configuration (ALPHA) 

## Installation
- Copy all the files into the root of your web server.
- Fix permission on cache folder (chmod 777 cache)
- Fix permission on config.php file. (chmod 777 config.php)
- Open the URL to your server in a browser and configure. http://SERVER_IP_ADDRESS/admin.php

## Upgrading
- Delete all files in the cache directory.
- Check permissions on cache and config.php.
