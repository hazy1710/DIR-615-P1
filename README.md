# Openwrt D-Link Dir-615 v.P1
![tag](https://github.com/hazy1710/DIR-615-P1/assets/19472123/6ff82bf7-beab-422d-9308-73b53b501364)
![gpio](https://github.com/hazy1710/DIR-615-P1/assets/19472123/1a123758-9db1-4b98-915c-eab087653168)
![gpio2](https://github.com/hazy1710/DIR-615-P1/assets/19472123/445be57b-b18b-4560-b431-9d5ab236de7f)


# Install
binutils bzip2 diff find flex gawk gcc-6+ getopt grep install libc-dev libz-dev
make4.1+ perl python3.7+ rsync subversion unzip which

# Download and unpacking
cd openwrt-19.07.10

# Update the feeds
./scripts/feeds update -a

./scripts/feeds install -a
 
# Configure the firmware image
make menuconfig
 
# Build the firmware image
make -j$(nproc) defconfig download clean world

# Load in router
By downloading quashfs-sysupgrade.bin via TFTP.
