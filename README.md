boot a fresh raspberry pi jessy strech


reference https://learn.adafruit.com/instant-camera-using-raspberry-pi-and-thermal-printer/system-setup


reference : http://scruss.com/blog/2015/07/12/thermal-printer-driver-for-cups-linux-and-raspberry-pi-zj-58/


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


```
sudo apt-get update 
sudo apt-get upgrade
sudo apt-get install git cups wiringpi build-essential libcups2-dev libcupsimage2-dev system-config-printer python-cups

```


```
sudo pip install pycups 
```

ajouter le printer dans CUPS

```
sudo lpadmin -p ZJ-58 -E -v serial:/dev/ttyAMA0?baud=19200 -m zjiang/ZJ-58.ppd
```

```
sudo usermod -a -G dialout pi
```

uncomment : disable overscan

activer le uart dans config.txt
```
enable_uart=1
```
reboot






