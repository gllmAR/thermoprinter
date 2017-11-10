boot a fresh raspberry pi jessy image



reference https://learn.adafruit.com/instant-camera-using-raspberry-pi-and-thermal-printer/system-setup


reference : http://scruss.com/blog/2015/07/12/thermal-printer-driver-for-cups-linux-and-raspberry-pi-zj-58/



```
sudo apt-get update 
sudo apt-get upgrade
sudo apt-get install git cups wiringpi build-essential libcups2-dev libcupsimage2-dev system-config-printer
```


sudo lpadmin -p ZJ-58 -E -v serial:/dev/ttyAMA0?baud=19200 -m zjiang/ZJ-58.ppd


sudo usermod -a -G dialout pi


activer le uart dans config.txt

enable_uart=1
reboot










install z83 build essential

```
sudo apt-get install libcups2-dev libcupsimage2-dev git build-essential cups system-config-printer

```


create a source folder

```
mkdir ~/src
```

clone repository in source folder

```
cd ~/src && git clone https://github.com/klirichek/zj-58.git
```

build it

```
cd ~/src/zj-58
make

```

install 

```
sudo ./install
```




Ensure that ttyAMA0 is not used for serial console access. 

Edit the file /boot/cmdline.txt to remove all name-value pairs containing ttyAMA0.
Add the user to the dialout group:

sudo usermod -a -G dialout pi
Reboot.


