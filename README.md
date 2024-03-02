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
