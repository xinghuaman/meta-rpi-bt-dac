# meta-rpi-bt-dac

Yocto layer to build Bluetooth DAC image for Raspberry Pi Zero W + pHAT DAC.

## Description

This layer extends the meta-raspberrypi BSP layer and builds a Linux image that allows to use Raspberry Pi Zero W and DAC hat as a Bluetooth audio sink. When the device is powered on, it will automatically become discoverable by Bluetooth. Pairing can be done without a pin, and the Pi is then recognized as a Bluetooth audio device (Advanced Audio Distribution Profile, A2DP).

## Hardware

[Raspberry Pi Zero W](https://www.raspberrypi.org/products/raspberry-pi-zero-w/)
[pHAT DAC](https://shop.pimoroni.com/products/phat-dac)

## Dependencies

This layer depends on:

* URI: git://git.yoctoproject.org/poky
  * branch: warrior

* URI: git://git.openembedded.org/meta-openembedded
  * layers: meta-oe, meta-networking, meta-python
  * branch: warrior

* URI: git://git.yoctoproject.org/meta-raspberrypi
  * branch: warrior

## Quick Start

1. Clone the dependencies and switch to correct branch
2. source poky/oe-init-build-env build
3. Add this layer to build/conf/bblayers.conf and the dependencies above
4. Set MACHINE in local.conf to raspberrypi0-wifi
5. bitbake core-image-base
6. dd to a SD card the generated sdimg file (build/tmp/deploy/images/raspberrypi0-wifi/core-image-base-raspberrypi0-wifi.rpi-sdimg)
7. Boot your RPI.