RTL8188FU driver for Linux kernel 4.15.x ~ >=6.3.x 

** info: rtl8188fu support (STA only ?) has been integrated in the rtl8xxxu module of the mainline kernel >= 6.2.0 <https://git.kernel.org/pub/scm/linux/kernel/git/torvalds/linux.git/commit/drivers/net/wireless/realtek/rtl8xxxu/rtl8xxxu_core.c?id=c888183b21f36a247bb166ca9365705611bea847> **


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

