RTL8188FU driver for Linux kernel 4.15.x ~ 6.1.x (Linux Mint, Ubuntu or Debian Derivatives)

** info: rtl8188fu has been integrated in the rtl8xxxu module of the mainline kernel >= 6.2.0 <https://git.kernel.org/pub/scm/linux/kernel/git/torvalds/linux.git/commit/drivers/net/wireless/realtek/rtl8xxxu/rtl8xxxu_core.c?id=c888183b21f36a247bb166ca9365705611bea847> **


------------------

## How to install

Install prerequisites (e.g., on Debian and derivatives):

`sudo apt-get install build-essential git dkms linux-headers-$(uname -r)`

then

`git clone https://github.com/alex14fr/rtl8188fu`

`cd rtl8188fu`

`make`

install with

`cp rtl8188fu.ko /lib/modules/$(uname -r)/`

`cp firmware/rtl8188fufw.bin /lib/firmware/rtlwifi/`

as root.

------------------

## Configuration

#### Disable Power Management

Run following commands for disable power management and plugging/replugging issues.

`sudo mkdir -p /etc/modprobe.d/`

`sudo touch /etc/modprobe.d/rtl8188fu.conf`

`echo "options rtl8188fu rtw_power_mgnt=0 rtw_enusbss=0" | sudo tee /etc/modprobe.d/rtl8188fu.conf`

#### Disable MAC Address Spoofing

Run following commands for disabling MAC Address Spoofing (Note: This is not needed on Ubuntu based distributions. MAC Address Spoofing is already disable on Ubuntu base).

`sudo mkdir -p /etc/NetworkManager/conf.d/`

`sudo touch /etc/NetworkManager/conf.d/disable-random-mac.conf`

`echo -e "[device]\nwifi.scan-rand-mac-address=no" | sudo tee /etc/NetworkManager/conf.d/disable-random-mac.conf`

#### Blacklist for kernel 5.15 and 5.16 (No needed for kernel 5.17 and up)

If you are using kernel 5.15 and 5.16, you must create a configuration file with following commands for preventing to conflict rtl8188fu module with built-in r8188eu module.

`echo 'alias usb:v0BDApF179d*dc*dsc*dp*icFFiscFFipFFin* rtl8188fu' | sudo tee /etc/modprobe.d/r8188eu-blacklist.conf`


------------------

