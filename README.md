## Linux Mainline Kernel for nanopi duo2

```sh
git clone https://github.com/gogogoghost/linux-nanopi-duo2 --depth=1

cd linux-nanopi-duo2

make ARCH=arm CROSS_COMPILE=arm-linux-gnueabihf- nanopi_duo2_defconfig

make ARCH=arm CROSS_COMPILE=arm-linux-gnueabihf- zImage

# do what you need
```

## Ethernet

Ethernet work well

## WLAN

Work well too

But need firmware for BCM43430

On alpine linux, install:

- linux-firmware-brcm
- linux-firmware-cypress
- wireless-regdb

## Bluetooth

Work well but I don't know why driver auto load brcm/BCM43430A1.hcd

This chip named ap6212, so I made a soft link from **/lib/firmware/ap6212/bcm43438a1.hcd** to **/lib/firmware/brcm/BCM43430A1.hcd**

Firmware will be loaded by auto and you don't need brcm_pathram_plus anymore.

## UART3/SPI1

I have disabled uart3 and enabled spi1 because I need it.
