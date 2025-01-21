## Using Download Managers / Torrent clients on Ubuntu

A Download Manager is a piece of software designed to help the internet user to effectively download and manage files from the internet. A good download manager ensures that downloads from the internet are much faster as compared to using the normal web browsers to download a file. A key feature associated with download managers is the ability to pause a download and resume the download at a later time. Further, a good download manager should support majority of internet protocols such as HTTP, HTTPS, FTP and many more.

**Torrents** are internet files that hold information about other files and folders that are to be distributed over the internet e.g movies, audio files, software, books and so on. Torrents contains information of where the data about a file or a folder are located. Torrents are powered by a file transfer protocal called **BitTorrent** that breaks down a huge file into smaller bits, transfers them over the internet into a user computer, and finally joins these bits into the same huge file in the users computer system.

Download Managers / Torrent Applications have the ability to schedule a download as well as allowing the internet user to download multiple files at once while controlling the bandwidth associated with each download. This means that it is easy to assign a higher bandwidth to a more urgent download to speed up the download time. 

Finally, a good download manager should have the ability to automatically recover from a network failure in case of a downtime. 

### 1. WebTorrent Desktop

WebTorrent Desktop is an open source Torrent Application for streaming torrents whether videos, music or audio books in real time without having to wait for the download. WebTorrent Desktop connects to both BitTorrent and WebTorrent peers. Being open source software, it is available for download for Mac, Windows and Linux users.

#### WebTorrent Desktop Features

- Lightweight

- Completely free & open source

- Easy to install and use

- It is developed in Node.js language.

- WebTorrent Desktop is based on webtorrent 

- WebTorrent instantly streams videos and audio files without having to wait for the download to finish.

- Stream videos to AirPlay, Chromecast, and DLNA

- WebTorrent is ad-free

- WebTorrent supports WebTorrent protocol for connecting to WebRTC peers i.e the browsers.

- WebTorrent discovers peers via tracker servers, Distributed Hash Table and peer exchange.

- The user easily drags and drops the downloadable file to easen the creation of torrents.
  
  ### Installation and usage
  
  Lets briefly look at installation and usage of WebTorrent on Ubuntu Desktop and its derivatives.
  
  #### Step 1 : Setup Preparation
  
  To begin the process of installation, prepare the Ubuntu Desktop and install some generic tools required for the installation of Download Managers covered in this documentation.
  
  ```bash
  sudo apt update && sudo apt upgrade
  sudo apt autoremove && sudo apt full-upgrade
  sudo apt install wget curl
  ```

#### Step 2: Download WebTorrent Desktop

Navigate to  [Github releases](https://github.com/webtorrent/webtorrent-desktop/releases) page for the latest release of WebTorrent Desktop to download the package.

This can be achieved in two ways:

The first method involves using curl to gitlab api to get the latest version of software dynamically as shown below.

```bash
cd Downloads/
VERSION=$(curl -s https://api.github.com/repos/webtorrent/webtorrent-desktop/releases/latest|grep tag_name|cut -d '"' -f 4|sed 's/v//')
```

In the above method, ***webtorrent*** is the github account ID while ***webtorrent-desktop*** is the repository.

The second method involves downloading the latest release by versioning it as below.

```bash
VERSION=0.24.0
wget https://github.com/webtorrent/webtorrent-desktop/releases/download/v${VERSION}/webtorrent-desktop_${VERSION}_amd64.deb
```

#### Step 3: Install WebTorrent Desktop

Install the WebTorrent Desktop package on Ubuntu system.

```bash
sudo apt install ./webtorrent-desktop_${VERSION}_amd64.deb
```

Check the version installed with the command below:

```bash
dpkg -s webtorrent-desktop | grep Version
```

#### Step 4: Launch WebTorrent Desktop

Launch WebTorrent Desktop by navigating to **Application menu** >> **Show Apps** >> search for **WebTorrent**

![WebTorrent-Launch.png](./images/WebTorrentimages/WebTorrent-Launch.png)

Alternatively, launch the application from the command terminal

```bash
webtorent-desktop
```

The launch opens the WebTorrent Desktop interface 

![WebTorrent-WebTorrent-Desktop-interface.png](./images/WebTorrentimages/WebTorrent-WebTorrent-Desktop-interface.png)

### Step 5: Using WebTorrent Desktop

WebTorrent Desktop allows the user to stream a torrent from his local machine or by using a magnetic link. Further, the user can create New Torrent from File, create New Torrent from a folder, open Torrent File as well as opening Torrent Address.

To stream a torrent from the localdisk, navigate to  **File** > **New Torrent from File** and select your Torrent as shown below.

<img title="" src="./images/WebTorrentimages/WebTorrent-Create-New-Torrent.png" alt="" width="609">

Click open to create a new Torrent.

![](./images/WebTorrentimages/WebTorrent-Create-New-Torrent.png)

Finally click **CREATE TORRENT** to create a new torrent

![](./images/WebTorrentimages/WebTorrent-Create-Torrent.png)

To download a magnetic torrent, navigate to **File** >> **Open Torrent Address**. You will be asked to supply the magnetic link or the torrent address. 

![](./images/WebTorrentimages/WebTorrent-Magnetic-link.png)

To explore more about WebTorrent, be sure to visit [WebTorrent GitHub page]() 

### 2. Tribler Download Manager

Tribler is an open source peer-to-peer file sharing program designed to ensure privacy using Tor-inspired onion routing. It is a torrent client that aims to protect the internet user against lawyer-based attacks and censorship. Tribler is a research project by Delft University of Technology that is continually improving upon BitTorrent protocol. It is a privacy enhanced BitTorrent client with P2P content discovery. If you are looking for a Download Manager that conceals your identity over the internet, then Tribler is a good pick. This is because Tribler doesnt use the normal Tor network but a dedicated Tor-like onion routing network for torrents download.

#### Features

Tribler Download Manager has key features as below.

- Ability to stream from magnet links.

- Ability to search for keywords in a content.

- Tribler is cross platform with installation packages available for Mac, Windows and Linux.

- Channels and reputation-management

- Its fully backwards compatible with BitTorrent

- Offers anonymous Torrent downloading with strong encryption

- Offers hidden seeding.

- It is open source and impossible to censor

- Uses a dedicated Tor-like onion routing network exclussively for Torrents download.
  
  #### Installation and Usage

Install Tribler on Ubuntu Desktop and its derivatives with the steps below.

##### Step 1 : Download the latest release of Tribler

To download the latest release of Tribler, navigate to Tribler [Github]() latest releases page and grab the package that fits your system architecture.

```bash
cd Downloads/
VER=8.0.7
wget https://github.com/Tribler/tribler/releases/download/v${VER}/tribler_${VER}_x64.deb
```

Alternatively, get the latest version of the software dynamically by "curling" to Gitlab api as below:

```bash
VER=$(curl -s https://api.github.com/repos/Tribler
/tribler/releases/latest | grep tag_name | cut -d '"' -f 4|sed 's/v//')
```

##### Step 2 : Install Tribler Download Manager

Install Tribler on Ubuntu Desktop system with the command below.

```bash
sudo apt -y install ./tribler_${VER}_x64.deb
```

Verify the version installed

```bash
apt list | grep tribler
## OR ##
dpkg --list | grep tribler
```

##### Step 3: Launch Tribler Application

Launch Tribler Download Manager on Ubuntu system by navigating to **Application Menu** >> **Show Apps** then search for **Tribler** on the search area.

![Tribler-Launch.png](./images/Triblerimages/Tribler-Launch.png)

Double click on Tribler icon to launch the Tribler web interface.

![Tribler-Web-Interface.png](./images/Triblerimages/Tribler-Web-Interface.png)

##### Step 4: Tribler Usage

The **+** **Add torrent** gives you the options to import torrent from magnet URL , import torrent from file(s) or to create torrent from file(s).

![Tribler-Add-Torrent.png](./images/Triblerimages/Tribler-Add-Torrent.png)

Choosing the import torrent from magnet/URL requires one to enter URL/magnetic link of the torrent you would like to download. 

![Tribler-Add-Torrent-From-URL.png](./images/Triblerimages/Tribler-Add-Torrent-From-URL.png)

Import torrent from file will require one to select a torrent from a file to import it to Tribler. Select the torrent  and Click **Open** to import the torrent to Tribler. You will be required to specify the download location for your video.

![Tibler-Import-Torrent-From-File.png](./images/Triblerimages/Tribler-Import-Torrent-From-File.png)

As discussed in the documentation above, you can search for a torrent using its keywords on the search area.

![Tribler-Torrent-Search.png](./images/Triblerimages/Tribler-Torrent-Search.png)

With Tribler, you are able to track your downloads in terms of the torrents being downloaded, the active torrents, the completed downloads as well as the inactive torrents. 

![Tribler-Download-Properties.png](./images/Triblerimages/Tribler-Download-Properties.png)

Addittionally, you are able to see the popular torrents as well as tweaking the bandwidth for torrents downloads under the settings tab.

![Tribler-Popular-Torrents.png](./images/Triblerimages/TriblerPopularTorrents.png)

To read more on Tribler, visit the official [Github page]([Releases · Tribler/tribler · GitHub](https://github.com/Tribler/tribler/releases)).

### 3. Motrix Download Manager

Motrix is a free and open source full-featured download manager that support torrent downloads from multiple protocols including HTTP, FTP, BitTorrent, Magnet and many more. Motrix is easy to install with an easy-to-use interface and packages for downloads and installation are available for Windows, Linux and macOS using the respective package managers.

Motrix supports a number of browser extensions like YAAW for chrome, Aria2 for chrome, Motrix chrome extension, Camtd and Aria2 DMI.

#### Features

Motrix Download Manager has the following features.

- Uses UPnP & NAT-PMP port mapping.

- Support BitTorrent & Magnet.

- Has an easy to use user interface.

- Motrix is cross platform.

- Selects the most optimal BitTorrent to download.

- Has a graph to track the download progress.

- Supports up to 10 concurrent downloads.

- Sends a notification upon completion of a download.

- Motrix updates a tracker list automatically everyday.

- Motrix has a mock user agent to assist the user.

- Supports dark mode feature.

- Related files can optionally be deleted when removing tasks.

#### Installation and usage

Installing Motrix on Ubuntu and its derivative is as simple as downloading the package and executing the package.

##### Step 1 : Download Motrix Download Manager

The latest Motrix releases can be downloaded on the official Github releases page.

```bash
cd Downloads/
VERSION=1.8.19
wget https://github.com/agalwood/Motrix/releases/download/v${VERSION}/Motrix_${VERSION}_amd64.deb
```

##### Step 2: Install Motrix Download Manager

The downloaded package is installed as below.

```bash
sudo apt install ./Motrix_${VERSION}_amd64.deb
```

Confirm the version installed.

```bash
dpkg --list | grep motrix
```

##### Step 3: Launch Motrix Application

Launch Motrix Application on Ubuntu by navigating to **Application Manager** >> **Show Apps** >> **search for Motrix** on the search bar.

![Motrix-Launch.JPG](./images/Motriximages/Motrix-Launch.JPG)

Double click the icon to open the user interface.

![Motrix-User-Interface.JPG](./images/Motriximages/Motrix-User-Interface.JPG)

To add a torrent for download purposes, click the **+** icon, then paste the URL to your torrent download. You can also drag and drop a torrent under **Torrent**

![Motrix-Add-Torrent.JPG](./images/Motriximages/Motrix-Add-Torrent.JPG)

To see more options, click the **settings** icon. On the **Appearance** you can choose your preffered theme, set up your preffered language and define the path to your downloads, specifying the bandwidth for transmission.

![Motrix-Advanced Settings.JPG](./images/Motriximages/Motrix-Advanced%20Settings.JPG)

Under **Advanced** tab, you can set up Proxy server as well as tracker servers, listening port should you decide to have custom listening ports. 

![Motrix-Advanced-Settings_two.JPG](./images/Motriximages/Motrix-Advanced-Settings_two.JPG)

In addition, you can set the default client for Magnet and Thunder protocols as well as specifying the Mock User-Agent e.g Mozilla, Chrome and Safari.

![Motrix-Advanced-Settings_three.JPG](./images/Motriximages/Motrix-Advanced-Settings_three.JPG)

Click Lab to view the **Featured Extensions** available for use with Motrix Download Manager.

![Motrix-Featured-Extensions.JPG](./images/Motriximages/Motrix-Featured-Extensions.JPG)

Get more details about Motrix on the official [Motrix Github page]([GitHub - agalwood/Motrix: A full-featured download manager.](https://github.com/agalwood/Motrix))

### 4: rTorrent Downloader Manager

rtorrent is an open source text-based BitTorrent client that is written in C++ high-level, general purpose programming language. rtorrent is based on **ncurses** and **lib Torrent** libraries for Unix. rtorrent transfers data directly between file pages mapped to memory by the mmap function. Preffered by many because of its high speed seeding capabilities on high bandwith connections. 

rtorrent is cross platform with packages available for installation for Linux, Unix, macOS, FreeBSD and Windows. rTorrent bittorrent is ideal for use with GNU Screen or Tmux and so can be run using commands on the terminal e.g carriage return to load a torrent, ^S to start a torrent, backspace to automatically a torrent once its loaded, ^K to stop a torrent, ^D to pause a torrent or to delete a torrent if torrent is already stopped or paused.

#### Features

Some of the features associated with rTorrent include the following.

- Supports saving of sessions allowing the user to add and remove torrents.

- Supports partial downloading of multiple torrents.

- Supports BitTorrent protocol encryption to enhance security of the torrents.

- Can be controlled via XML-RPC over SCGI.

- rTorrent is free and open source and licensed under GPL-2.0 or later with OpenSSL exception.

- rtorrent is cross platform.

- Supports high speed seeding of torrents

- rTorrent is ideal for use with tmux, screen or dtach

- rTorrent has a built-in daemon mode for disabling the user interface.

#### Installation and Usage

Use the steps below to install rTorrent on Ubuntu Desktop and its derivatives.

##### Step 1 : Download rTorrent installation package

The rTorrent package is available in the APT package index for Ubuntu and its derivatives. However, packages exist for those who wishes to built the application from the source code. 

In this documentation, we will use the packages available in the APT package index. Search the package by the following command:

```bash
apt search rtorrent
```

##### Step 2: Install rTorrent on Ubuntu Desktop

Install the rTorrent package by running the command below:

```bash
sudo apt install rtorrent
```

The command installs all the required dependencies needed to install rTorrent on your Ubuntu Desktop.

Check the installed version:

```bash
sudo apt-cache show rtorrent | grep Version
```

##### Step 3: Launch rTorrent on Ubuntu Desktop

To launch rtorrent, simply execute the command rtorrent on the terminal

```bash
rtorrent
```

This command opens a terminal where the user can now run the commands. However, a few tweaks must be done inorder to use the terminal to download your torrents. 

###### 1. Locate the rTorrent file in your system

The rtorrent file is by default located in **/usr/share/doc/rtorrent/examples** . Change directory to this location to locate the file.

```bash
cd /usr/share/doc/rtorrent/examples
```

###### 2. Copy the file to your home directory

The contents of the folder is a file named **rtorrent.rc.gz**. This is the default configuration file for rtorrent. As root user, you can read the file. Make the file writable and rename it then copy the file to home directly

```bash
sudo vim rtorrent.rc.gz
## Rename the file 
:w /home/user/.rtorrent.rc
:wq
```

Navigate to home directly and list the hidden files.

```bash
cd ~
ls -la | grep .rtorrent
```

###### 3. Change Ownership of the file

The copied file by default belongs to root user. Change the ownership of the file to system user and the user group:

```bash
sudo chown user:user .rtorrent.rc  
```

###### 4. Make necessary configurations to the file

To use rTorrent open the file with our favorite text editor and make the follwing configurations to the file.

```bash
vim .rtorrent.rc

# Default directory to save the downloaded torrents.
directory.default.set = ./Downloads
## Set the default session directory to save your sessions
session.path.set = ./session
# Watch a directory for new torrents, and stop those that have been deleted.
schedule2 = watch_directory,5,5,load.start=./watch/*.torrent
# Enable DHT support for trackerless torrents
dht.mode.set = on
# UDP port to use for DHT.
dht.port.set = 6881
```

After making the changes save and exit from the file

```bash
:wq
```

Create the session and watch folders in your home directory for storing your sessions and schedules respectively.

```bash
mkdir session && mkdir watch
```

When all the changes have been made, launch the application on the command line interface by running the following command

```bash
rtorrent
```

The command will open the user CLI interface:

![](C:\Users\pndungu\AppData\Roaming\marktext\images\2025-01-15-16-48-44-image.png)

##### Step 4: rTorrent Usage

To add a torrent, grab your torrent from the internet, and **save the link as** on the **watch** directory created above.

![](C:\Users\pndungu\AppData\Roaming\marktext\images\2025-01-15-17-54-33-image.png)

As below:

![](C:\Users\pndungu\AppData\Roaming\marktext\images\2025-01-15-17-58-08-image.png)

You will see the download progressing.

![](C:\Users\pndungu\AppData\Roaming\marktext\images\2025-01-15-18-05-52-image.png)

The **session** folder logs all the rTorrent logs.

![](C:\Users\pndungu\AppData\Roaming\marktext\images\2025-01-15-18-29-13-image.png)

To see a detailed list of the commands on rTorrent, use the command.

```bash
man rtorrent
```

Read more on rTorrent on the official [Github](https://github.com/rakshasa/rtorrent) page

### 5. qBittorrent Download Manager

qBittorent is an open source software an alternative to uTorrent based on the Qt toolkit and libtorrent-rasterbar library. It is supported by all major platforms i.e Linux, macOS, Windows and FreeBSD. Being open source, it has a huge community of users who contribute regularly to their forums to help new users acclimatise very speedily. The forums also provide users with answers to challenges they might encounter during qBittorrent usage.

#### Features

qBittorrent volunteer developers are continually improving on the software. Some of the common features associated with qBittorrent are as below:

- Has a polished user interface making it easy to use.

- Has a well integrated and extensible search engine.

- The user is not interfered with Ads.

- Supports many Bittorrent extensions e.g magnet links, private torrents and so on

- Support RSS feed with advanced download filters.

- Supports remote control through web user interface.

- Downloads torrents in sequence and in order.

- Has advanced control over torrents, trackers and peers.

- Supports torrents content selection, queueing and prioritizing.

- Supports bandwidth scheduling

- Has ability to filter IP's and is IPv6 compliant.

- Supports UPnP and NAT-PMP port forwarding.

- It is cross-platform

- Supported by multiple languages.

- Has ability to simultaneously search in many torrent search sites.

- With qBittorrent you are able to search for torrents using categories e.g books, music, videos and so forth.

#### Installation and Usage

To install qBittorrent on Ubuntu Desktop and its derivatives, follow the steps below.

##### Step 1 : Download qBittorrent package

[uBittorrent download packages](https://www.qbittorrent.org/download) are available for download on the official website. The website keeps both nightly builds and beta packages. Scroll down to Linux section and download the AppImage suitable for your Ubuntu distribution. Beta version is not stable and its advisable to download the stable version. For users who like to build from source files, they can download the binary packages and install.

qBittorrent packages are available for download and installation on APT package index. This is the simplest method of installation as it only requires you to install the package from the apt repository.

To see if the package is available in your distribution, search the package by running the command below:

```bash
apt search qBittorrent
```

##### Step 2: Install qBittorrent package

Use APT package manager to install the package.

```bash
sudo apt install qbittorrent
```

This command installs all the dependencies required to successfully install qBittorrent in Ubuntu desktop.

##### Step 3: Launch qBittorrent

To launch qBittorrent, navigate to  **Applications Launcher**  and search for qbittorrent on the search bar. Double click on the qBittorrent icon to launch it.

![](C:\Users\pndungu/Download%20Managers/Cloudspinx/qBittorrent%20Images/qBittorrent-Launch.JPG)

When launching the qBittorrent application for the first time, you will be prompted to Agree with the Legal notice that warns you that any content you share is your sole responsibility.

![](C:\Users\pndungu\Download%20Managers/Cloudspinx/qBittorrent%20Images/qBittorrent-Legal-notice.JPG)

Click **I Agree** button.

This opens the user interface page:

![](C:\Users\pndungu\Download%20Managers/Cloudspinx/qBittorrent%20Images/qBittorrent-User-Interface.JPG)

To use qBittorrent, navigate to **File** menu to see the options to ***Add Torrent File*** as well as ***Add Torrent Link***.

![](C:\Users\pndungu\Download%20Managers/Cloudspinx/qBittorrent%20Images/qBittorrent-File-Menu.JPG)

Under the **Edit** tab on the Menu, this is where you control your downloads. You can either Resume, Pause, Resume All, Pause All or Remove the torrents.

Under **Preferences** you can change the **behavior** of your interface. You can alter your **Downloads** by specifying the paths to your downloads and many more features. Under **Connection** you can define your listening port, setup a proxy server, define your hosts, do IP filtering as well as setting up authentication for your connections.

Under **Speed**, you can set the Global uploads and download speeds, set alternative rate limits and schedule the use of alternative rate limits. Under **BitTorrent** you specify the privacy or even enable anonymous encryption mode. In addition, you are able to setup torrent queueing by defining the maximum active downloads at a time, maximum active uploads and maximum active torrents. Enabling fetching RSS feeds is possible under **RSS** . Other features are **Web UI**  that allows the user to setup remote control, setup SSL certificates to use instead of using HTTP, setting up IP subnet whitelist and many more features. The **Advanced** tab carries all the settings you would wish to make like adjusting physical memory, setting up notifications, binding IP addresses and many other settings.

Check the official [qBittorrent Github](https://github.com/qbittorrent/qBittorrent/wiki/) for more about qBittorrent, 



### 6. Gopeed Download Manager

Gopeed (Go Speed) is a cross-platform, lightweight, high speed, Open source modern download manager with an intuitive User Interface for downloading torrents. Gopeed is built using Golang and Flutter and supports HTTP, BitTorrent, Magnet protocols. It is highly customizable  allowing the user to implement more features through integration with APIs or installation & development of extensions.

#### Features

A brief of the common features associated with Go Speed modern downloader manager is as below.

- Gopeed supports HTTP & HTTPS, protocols

- Supports BitTorrent and  Magnet.

- Gopeed is cross-platform in natures ( supports Windows, Linux, Android)

- Highly customizable

- Supports dark mode

- Automatic update of the tracker list

- Its easy to interact with Gopeed via Open HTTP API.

- Has a decentralized customizable extensions.

- It is completely free and non-electron.

- It is fast.

#### Installation and Usage

The latest Release packages are available for download at the official Gopeed [GitHub Releases](https://github.com/GopeedLab/gopeed/releases) page. To install Gopeed on Ubuntu Desktop:

##### Step 1: Download the package

Navigate to the release page and grab the latest installation package.

```bash
cd Downloads
VER=1.6.7
wget https://github.com/GopeedLab/gopeed/releases/download/v${VER}/Gopeed-v${VER}-linux-amd64.deb
```

##### Step 2: Install the package

Installing the latest Gopeed package on Ubuntu is a straight forward process. Run the command below.

```bash
sudo apt install ./Gopeed-v${VER}-linux-amd64.deb
```

##### Step 3: Launch the Application

To launch the application, navigate to **Applications Menu** >> **Shows Apps** >> Search for **Gopeed**

![](C:\Users\pndungu\AppData\Roaming\marktext\images\2025-01-17-17-12-44-image.png)

The user inteface looks like this:

![](C:\Users\pndungu\AppData\Roaming\marktext\images\2025-01-17-17-14-20-image.png)

##### Step 4: Usage

To add a torrent link, click the  **+** sign on the bottom right corner and paste your download link then click **Confirm** to begin your download.

![](C:\Users\pndungu\AppData\Roaming\marktext\images\2025-01-17-19-24-23-image.png)

The progress of the download can be tracked.

![](C:\Users\pndungu\AppData\Roaming\marktext\images\2025-01-17-19-34-50-image.png)

You can pause the download, delete the download and resume to a download at a later time.

Under **Settings** you can set up several options like the *Download Directory*, set the *maximum number of running tasks*, set *Browser Extensions*, setup *HTTP User-Agent*, set *BitTorrent Port number*, change the *Theme color*, Language and you could also see the *Version* you are running on.

In the Advanced Tab, you can setup your proxy server as well as setup the [API](https://docs.gopeed.com/dev-api.html#using-http-api) Integration. Gopeed provides an HTTP API interface which allows the user to download and manage downloads through the API. To set up the HTTP API, navigate to **Settings** >> **Advanced** >> **Protocol** . Ensure the API protocol is set to TCP, then specify the IP Address of your proxy and the port number.

![](C:\Users\pndungu\AppData\Roaming\marktext\images\2025-01-17-19-52-42-image.png)

Read more on Gopeed on the official [Gopeed Github page]([GitHub - GopeedLab/gopeed: A modern download manager that supports all platforms. Built with Golang and Flutter.](https://github.com/GopeedLab/gopeed)).













### 6. Transgui Download Manager

Transmission Remote GUI is a user-friendly, front-end software rich in features used to remotely control the Transmission BitTorrent daemon client via its RPC protocol. It is cross-platform GUI, that is faster with more functionalities than builtin Transmission web interface. Its written in Lazarus RAD and Free Pascal compiler.

Transgui works by connecting to the Transmission BitTorrent daemon running on your server. Once the connection is established, the user is able to control the Transmission BitTorrent daemon as well as manage the torrents remotely.

#### Key Features of Transgui

Some of the features associated with Transgui are as highlighted below:

- You are able to remotely manage the Transmission BitTorrent daemon client from anywhere in your network or over the internet.

- Transgui is cross-platform in nature.

- Transgui has an intuitive and easy to use friendly user interface.

- Transgui is faster in torrents download than the built-in transmission web interface.

- Transgui gives priorities to torrents and files.

- The user can select his preffered language to use on the dashboard.

- Allows you to select files to download.

- Gives the user the tracker details.

- Gives information about each torrent.

- Filters torrents by status, tracker, folder and so on.

- Gives alerts when download is complete.

- Gives details on the connected peers.

- Has ability to display peers country flag.

#### Installation and Usage

The latest releases for download are available on the [Github Releases]([Releases · transmission-remote-gui/transgui · GitHub](https://github.com/transmission-remote-gui/transgui/releases)) page for various distributions. These packages are for building the application from source code. 

Precompiled program binaries for i386 and x86_64 Linux architectures exist in package managers for these Linux architectures. For this documentation we will use this method.

##### Step 1 : Install Transgui on Ubuntu Desktop

To install Transmission Remote GUI on Ubuntu Desktop and its derivatives, first ascertain if the package is available in the APT package index.

```bash
apt search transgui
```

Install the package:

```bash
sudo apt install transgui
```

All the required dependencies necessary for Transgui installation are installed as the application is installed from the official Transgui package from Ubuntu repositories.

Check the version installed:

```bash
apt show transgui | grep Version
```

##### Step 2: Launch Transgui

Launch the Transgui application by navigating to **Applications Manager** >> **Show Apps** >> search for **Transmission Remote GUI** 

![](C:\Users\pndungu\AppData\Roaming\marktext\images\2025-01-16-17-19-54-image.png)

Double click on the icon to launch the application.

![](C:\Users\pndungu\AppData\Roaming\marktext\images\2025-01-16-17-21-57-image.png)
