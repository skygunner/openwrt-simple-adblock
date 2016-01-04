# OpenWrt Simple Adblock
A simple DNSMASQ-based adblocking script for OpenWrt. Shamelessly stolen from bole5 at OpenWrt forums (https://forum.openwrt.org/profile.php?id=45571) with some performance and additional lists improvements.

# How to use
Run the following commands after you ssh (For Linux/Mac use built-in ssh client, for Windows try putty) to your router:
```bash
wget --no-check-certificate -qO /tmp/adblock-install.sh https://raw.githubusercontent.com/stangri/openwrt-simple-adblock/master/adblock-install.sh
chmod +x /tmp/adblock-install.sh
/tmp/adblock-install.sh
```

# Known Issues
By default the config setup includes four very large lists. It might cripple/break older routers with little RAM/Flash. Check the *adblock-install.sh* script for comments and feel free to remove the lists you don't want.

I get weird 'command not found' error on */etc/init.d/adblock stop*, I have no idea what's causing this (procd maybe?), but the script runs fine.

The script manipulates the /etc/banner file to reflect the status of the adblock _if_ the */etc/banner.orig* file exists. The install script creates this file at the last line, comment it if you want to keep your banner unchanged.
