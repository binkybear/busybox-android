Busy for Android modified by Binkybear
Original fork: Alexandre Courbot <acourbot@nvidia.com>
=====

## How to build your own busybox from Android (tested on Ubuntu)

Change the <username> to your username or if you are root change path to /root

```bash
# Toolchain installation
cd <username>
git clone https://github.com/Christopher83/arm-cortex_a7-linux-gnueabihf-linaro_4.9.git toolchain
export CROSS_COMPILE=/home/<username>/toolchain/bin/arm-cortex_a7-linux-gnueabihf-

# Build Busybox
git clone --recursive https://github.com/binkybear/busybox-android.git
cd busybox-android/busybox
patch -p1 ../busybox-android.patch
cp ../busybox-android.config .config
make menuconfig # If you want to modify binary
make
```