# rpi-debian-config
Configure debian on Raspberry pi 3

# Debian
Download Debian image (Family 3 3B+) [image](https://raspi.debian.net/tested-images/)

Write image to SD Card with [Win32DiskImager](https://sourceforge.net/projects/win32diskimager/)

Put SD Card in Raspberry Pi and power up.

# Root login
Debian is configure with root without password

# Wifi
Edit /etc/network/interfaces.d/wlan0 as below (replace SSID/PSK with your wifi id)

```Console
auto wlan0
iface wlan0 inet dhcp
    wpa-ssid <SSID>
    wpa-psk <PSK>
```

# SSH
## SSH setup
TBD

## SSH root login
Edit /etc/ssh/sshd_config, add in config:
```console
PermitRootLogin yes
```

Restart sshd daemon
```shell
$ systemctl restart sshd
```

# Keyboard
Change Keyboard layout with:
```Console
$ dpkg-reconfigure keyboard-configuration
```
