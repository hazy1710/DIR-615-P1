# Openwrt D-Link Dir-615 v.P1
![gpio](https://github.com/hazy1710/DIR-615-P1/assets/19472123/1f80bcc3-ce92-4748-aa77-0e62b166be2b)
![tag](https://github.com/hazy1710/DIR-615-P1/assets/19472123/20b30b69-2ea6-46d9-a561-686f6bf4bafa)
![gpio2](https://github.com/hazy1710/DIR-615-P1/assets/19472123/606dac82-57b7-405f-b0a3-a97ce599cb17)



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
