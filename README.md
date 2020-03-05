# libusb-1.0.22

script for configure and then a correct libusb-1.0.so file is generated whose architecture was for arm(raspberry pi3).

./configure CC=/home/yasir/Development/crosscompile/tools/arm-bcm2708/gcc-linaro-arm-linux-gnueabihf-raspbian-x64/bin/arm-linux-gnueabihf-gcc  --host=arm-linux --enable-udev=no --enable-shared  --prefix=/usr/local/libusb-rpi



./configure CC=/opt/reach/1.6/sysroots/i686-reachsdk-linux/usr/bin/arm-reach-linux-gnueabi/arm-reach-linux-gnueabi-gcc --host=arm-linux --enable-udev=yes -enable-shared --prefix=/usr/local/libusb 
