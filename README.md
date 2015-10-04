# PCD8544
#Library to LCD Display PCD8544 Shield v2.0 (By ArduinoKing.com) for Raspberry Pi 2 with a CPU and IP System Info

A simple PCD8544 LCD (Nokia3310/5110) driver. Target board is Raspberry Pi Model B+. 
This driver uses 5 GPIOs on target board with a bit-bang SPI implementation (hence, may not be as fast but seems fast enough). The pcd8544_rpi.c tool, to be compiled, allow you to display CPU and IP info on LCD Display. 
Makes use of WiringPI-library of Gordon Henderson (https://projects.drogon.net/raspberry-pi/wiringpi/)

#Requirements

- Rasbian Linux last version (use sudo apt-get update) - February 25th 2015 or later 
- This makes use of WiringPI-library of Gordon Henderson - so the WiringPI-library is required to be installed.
- The GCC (GNU C Compiler) release 5.2.

#Usage

1) If the WiringPi is not installed, please do this:

cd /

git clone git://git.drogon.net/wiringPi

cd /wiringPi

./build

2) After this copy the PCD8544 directory downloandig this library file zip to a directory of you free choose.
Example:

cd /

mkdir PCD8544

cd PCD8544

git clone git://github.com/gtrento/PCD8544

The PCD8544.c and PCD8544.h files is a library, the pcd8544_rpi.c is a file example to show on a LCD display the system informations like Uptime, CPU percent use, RAM memory use (MB) and the DHCP IP address number.

3) Since GCC is installed on Raspberry Pi images, you can easily build them using the command:

$ cc -o cpushow pcd8544_rpi.c PCD8544.c  -L/usr/local/lib -lwiringPi

or only

$ cc -o cpushow pcd8544_rpi.c PCD8544.c -lwiringPi

4) Run the cpushow typing in linux prompt:

./cpushow

Obs.: If you need to change brightness on the LCD, then you need to make changes to pcd8544_rpi.c:

vi pcd8544_rpi.c

//lcd contrast

Default is 45, if it is too dark lower it, otherwise increase the value (I used to 65). Else, decrease the value.


More about:

PCD8544 LCD SHIELD: http://lovebookstore.com/amazon_store/item/B00NKAME8S

WIRING PI: https://projects.drogon.net/raspberry-pi/wiringpi/

Other librarys: https://github.com/ronanguilloux/Raspberry-Pi-Utils

