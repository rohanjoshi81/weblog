---
title: "Setup your personal streaming service - using Plex, Sonarr, Radarr and Jackett"
date: 2021-03-10T12:00:00+05:30
categories:
  - blog
tags:
  - guide
  - tech
---

This is a very basic guide to help you setup your own streaming service on Windows 10 or 11. There are better detailed guides out there especially for Linux.

The idea is to setup a media server and then automate it to download media and make it viewable from anywhere in least possible clicks. You just need a dedicated device capable of running a modern OS, an old laptop is enough. I am using a 2013 Asus X550CL lapotop with i3 3rd gen and 4 gigs of Ram as my server. It is best to connect the server to router via Ethernet cable.

Here are the softwares we will be using 

- Plex Media server
- Sonarr - for searching tv shows
- Radarr - for searching movies
- Jackett - for adding indexer for both Sonarr/Radarr
- A torrent client ( Qbittorrent )
- A browser ( Brave, Firefox or Opera - personal choice )
- A VPN ( optional )

Everything except Plex is optional if you don't want to download content from the internet and use your own personal media files.

# Steps

- Format your system and install fresh copy of Windows 10

- Download plex from - https://www.plex.tv/media-server-downloads/

- Open Plex Media server on browser and Sign up to plex. Follow the first time setup and set media folders. By default there will be Photos, Videos and Music. You can create other folders like Home Videos or TV Shows as per  your need. If you have any media files you can copy to these folders.

- From any other device - other computer, Android/iPhone, Smart tv install the Plex client and login to access your server. You will be able to stream the media content from any device on the same wifi network. In case you want to stream the content remotely ( outside you local network ) just Enable Remote Access in Settings > Server > Remote Access from the Plex media server.

Ok so our media server is ready. You can put any file in the library folders on server and it will be streamable across your client devices.

You can stop here if your need is fulfilled. Continue if you want to automate this server to download content for you and make available to stream.

- Install a torrent client preferable Qbittorrent https://www.qbittorrent.org/download . Open setting > Enable Web UI , change the port if needed and set a username and password. Open the localhost: port with credentials

- Install Jackett from https://github.com/Jackett/Jackett/releases , enable it as a Windows service. Double clicking it will open it in browser, now we need to add a indexer so choose from the multiple options and add the preferable one ( You may need a account for this ). After saving, You will see a indexer on main page. Click on Torznab feed button and copy the API key from the same page.

- Install Sonarr from https://sonarr.tv/#download , enable it as a Windows service. Open it ( it will again open in browser ) and configure these settings - Media Management ( Choose the root folders which will be same as Plex media folders ) , Profiles ( set the preferred quality of file , language ) , Indexers ( Add Torznab as a new index - in URL/API Key fields set the feed URL/key copied from Jackett indexer ) , Download Clients ( choose Qbittorrent - set the host , port , username , password )

- Install Radarr from https://radarr.video/#download and follow the similar steps to Sonarr to set it up.

# Testing

- Now go to Sonarr/Radarr home page, click on Add new and search for any movie or tv show. Click on your selection and then choose preferred settings - default ones should work fine. Then click on the green Add button. 

- After couple minutes , Go to Qbittorrent and you will see the file is queued or started downloading. You may need a VPN at this step if your ISP has blocked the indexer you are trying to fetch from. You can use the test button while configuring jackett/sonarr/radarr to see if connection is working.

- Once the file is downloaded go to Plex media server and you should be able to see the media files there ( in case not appearing just scan library ) 

- Now you can connect from any client device and stream the content.

Disclaimer : You Wouldn't Steal a Car. The author condemns piracy and this guide is for legal content only.

# Troubleshooting

Some issues I faced and their solutions -

- Not able to select root directory in radarr/sonarr - Go to services.msc search for the service, In Properties > Log On check the first option and restart the service.

- Sonarr / Radarr selected download file size is too large - Go to Quality setting in and to limit the size of download file based on each profile.

- No download in torrent client even after selecting from sonarr / radarr - This can be due to multiple issues like your defined profile filters not being matched in the indexer ( I once faced this issue when the video language was not matched to the videos found by indexer ). To identify the exact issue go to Logging settings and set logger level to Debug , then you can download the log file and see the exact reason why your download is not starting. 

Hopefully you are able to setup your own media server using this and enjoy your content on the go! Connect with me for any help!
