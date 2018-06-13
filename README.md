# hatOLED
1.3inch OLED HAT

SOURCE: https://www.waveshare.com/wiki/1.3inch_OLED_HAT

```
sudo raspi-config
```
> Select: Advanced Options -> SPI -> ye

##### Install WiringPi Library
> https://projects.drogon.net/raspberry-pi/wiringpi/download-and-install/
```
sudo apt-get install git-core
sudo apt-get update
sudo apt-get upgrade

git clone git://git.drogon.net/wiringPi
cd wiringPi
git pull origin
cd wiringPi
./build
```

> Test wiringPi’s installation 
``run the gpio command to check the installation:``
```
gpio -v
gpio readall
```

##### Install C Library bcm2835
> http://www.airspayce.com/mikem/bcm2835/
```
wget http://www.airspayce.com/mikem/bcm2835/bcm2835-1.56.tar.gz
tar zxvf bcm2835-1.56.tar.gz
cd bcm2835-1.56
./configure
make
sudo make check
sudo make install
```
> To enable device tree support:
sudo raspi-config
under Advanced Options - enable Device Tree
Reboot.

##### Install Python Library
```
sudo apt-get update
sudo apt-get install python-dev
sudo python setup.py install
sudo apt-get install python-smbus
sudo apt-get install python-serial
sudo python setup.py install
sudo apt-get install python-imaging
```

```
sudo apt-get install python-dev python-pip libfreetype6-dev libjpeg-dev
sudo -H pip install --upgrade pip
sudo apt-get purge python-pip 
sudo -H pip install --upgrade luma.oled
```

##### Configuring the interfaces
> https://www.waveshare.com/wiki/Libraries_Installation_for_RPi
```
sudo raspi-config
sudo nano /etc/modules
Add the following two lines to the configuration file
    i2c-bcm2708 
    i2c-dev 
sudo raspi-config
    Select Advanced Options -> Serial. Select the option no can disable the serial debugging function.
sudo raspi-config
    Select Advanced Options -> I2C -> yes, to start up I2C core driver. 
```

DEMO
----
> https://www.waveshare.com/w/upload/4/46/1.3inch_OLED_HAT_User_Manual_EN.pdf
```
wget https://www.waveshare.com/w/upload/d/d5/1.3inch-LCD-HAT-Code.7z
cd 1.3inch-LCD-HAT-Code
sudo python demo.py
```
