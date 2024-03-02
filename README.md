# Openwrt D-Link Dir-615 v.P1
![gpio](https://github.com/hazy1710/DIR-615-P1/assets/19472123/1f80bcc3-ce92-4748-aa77-0e62b166be2b)
![tag](https://github.com/hazy1710/DIR-615-P1/assets/19472123/20b30b69-2ea6-46d9-a561-686f6bf4bafa)
![gpio2](https://github.com/hazy1710/DIR-615-P1/assets/19472123/606dac82-57b7-405f-b0a3-a97ce599cb17)

# Прошивка по TFTP
Подключаемся через UART (скорость:57200)
Подключаемся через Ethernet
ПК IP 192.168.0.2
Положить в папку сервера TFTP файл dir-615-p1-squashfs-sysupgrade.bin
Запускаем на ПК TFTP сервер 192.168.0.2 
Включаем роутер ждем сообщения:
1: Load system code to SDRAM via TFTP.
2: Load system code then write to Flash via TFTP.
3: Boot system code via Flash (default).
4: Entr boot command line interface.
7: Load Boot Loader code then write to Flash via Serial.
9: Load Boot Loader code then write to Flash via TFTP.

Жмем 2

ou choosed 2
... 0
raspi_read: from:40028 len:6
2: System Load Linux Kernel then write to Flash via TFTP.
Warning!! Erase Linux in Flash then burn new one. Are you sure?(Y/N)

Жмем Y

Please Input new ones /or Ctrl-C to discard
.Input device IP (192.168.0.1) ==:192.168.0.1

Жмем Enter

.Input server IP (192.168.0.2) ==:192.168.0.2

Жмем Enter

.Input Linux Kernel filename () ==:

Пишем имя файла прошивки в папке TFTP например dir-615-p1-squashfs-sysupgrade.bin
Ждем окончания прошивки.
default IP 192.168.1.1

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
