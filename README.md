# wifi-connect-headless-rpi
An application written in python that displays a wifi configuration UI for the reaspberry pi zero devices.   The installation program is written to work even when you only have a headless (wifi) connection to the reaspberry pi zero.    

Please see the complete writeup at the [www.surfncircuits.com Simplifying WiFi connections for Raspberry Pi Zero W projects ](https://surfncircuits.com/?p=5953) blog: 

Inspired by [wifi-connect](https://github.com/balena-io/wifi-connect) project written by [balena.io](https://www.balena.io/) and forked from the [python-wifi-connect](https://github.com/OpenAgricultureFoundation/python-wifi-connect) written by [OpenAgricultureFoundation](https://github.com/OpenAgricultureFoundation) .

# Install and Run

Please read the [INSTALL.md](INSTALL.md) then the [RUN.md](RUN.md) files.

# How it works
![How it works](./docs/images/how-it-works.png?raw=true)

WiFi Connect interacts with NetworkManager, which should be the active network manager on the device's host OS.

### 1. Error:  No valid WiFi network

At boot, a valid WiFi network is not found

### 2. Advertise: Device Creates Access Point

WiFi Connect detects available WiFi networks and opens an access point with a captive portal. Connecting to this access point with a mobile phone or laptop allows new WiFi credentials to be configured.

### 3. Connect: User Connects Phone to Device Access Point

Connect to the opened access point on the device from your mobile phone or laptop. The access point SSID is, by default, `Rpi-hostname` where hostname if the device name. 

### 4. Portal: Phone Shows Portal to User in Web Browser

After connecting to the access point from a mobile phone, it will detect the captive portal and open its web page. Opening any web page will redirect to the captive portal as well.  The default IP address is 192.168.42.1

### 5. Credentials: User Enters Local WiFi Network Credentials on Phone

The captive portal provides the option to select a WiFi SSID from a list with detected WiFi networks and enter a passphrase for the desired network.

### 6. Connected!: Device Connects to Local WiFi Network

When the network credentials have been entered, WiFi Connect will disable the access point and try to connect to the network. If the connection fails, it will enable the access point for another attempt. If it succeeds, the configuration will be saved by NetworkManager.

# Details
* [Installation and Demo](https://youtu.be/kttueMbMtCQ)
