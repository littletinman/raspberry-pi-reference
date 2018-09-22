# Setup Wifi on Raspberry Pi Without Monitor
This will explain how to enable wifi before ever booting your Raspberry Pi and without the need for a monitor and keyboard attached to the Raspberry Pi

1. Download Image from Raspberry Pi [website](https://www.raspberrypi.org/downloads/raspbian/)
2. User [Etcher](https://etcher.io/) to write to sdcard
3. After writing is complete, re-insert the sdcard into the computer
4. Go to the storage drive called ```boot```
5. Add ```ssh``` file with no content
6. Add ```wpa_supplicant.conf``` with the following content:
```
country=US
ctrl_interface=DIR=/var/run/wpa_supplicant GROUP=netdev
update_config=1

network={
 ssid="WIFI_SSID"
 scan_ssid=1
 psk="WIFI_PASSWORD"
 key_mgmt=WPA-PSK
}
```
7. Unmount drive and put in Raspberry Pi
8. Boot Raspberry Pi and wifi should connect automatically

**Note**: Tested on 2018-06-27-raspbian-stretch
**Credit**: Derived from [www.losant.com/blog](https://www.losant.com/blog/getting-started-with-the-raspberry-pi-zero-w-without-a-monitor)