## Commands for install TendaU9 drivers for Linux ##

### apt(Ubuntu) package manager: ###  
sudo apt update  
sudo apt install build-essential git dkms  
git clone https://github.com/brektrou/rtl8821CU.git  
cd rtl8821CU  
chmod +x dkms-install.sh  
sudo ./dkms-install.sh  
sudo modprobe 8821cu 

### pacman(arch) package manager: ###  
Build and install without DKMS:  
https://linuxconfig.org/manjaro-linux-kernel-headers-installation - про headers   

https://github.com/brektrou/rtl8821CU - сам драйвер, устанавливал через Makefile, если устанавливать через dkms:  
sudo pacman -S dkms - то надо установить эту утилиту

pacman -Q | grep headers  
uname -r - обратить внимание на версию(пример у меня версия - 5.8.18-1-MANJARO, запоминаю первые 2 цифры 5.8)  
sudo pacman -S linux-headers - тут нужно выбрать какой версии header установить(в уме 5.8 его и надо установить)  
reboot  
git clone https://github.com/brektrou/rtl8821CU.git  
cd rtl8821CU  
make  
sudo make install  
reboot
