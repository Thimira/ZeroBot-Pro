# ZeroBot Pro
Raspberry Pi Zero FPV Robot

## Raspberry Pi Compatibility
Works with Raspberry Pi Zero W and Zero 2 W

## OS Tested
Raspberry Pi OS (Legacy) Light - Debian Bullseye - Release date: 2023-05-03

## Setup Commands

First, run an update
```
sudo apt-get update
sudo apt-get upgrade
```

Enable legacy camera support in raspi-config
```
sudo raspi-config
```

Install Apache, Node.js, and NPM
```
sudo apt-get install apache2 node.js npm
```

Clone the repository and install the npm dependencies 
```
git clone https://github.com/Thimira/ZeroBot-Pro.git ~/touchUI
cd ~/touchUI

sudo npm install express
sudo npm install socket.io
sudo npm install node-ads1x15
sudo npm install coffee-scrip
```

Install the pigpio C library first, followed by the pigpio npm libraries
```
sudo apt-get install pigpio

sudo npm install pi-gpio
sudo npm install pigpio
```

Install dependencies for mjpg-streamer
```
sudo apt-get install libjpeg62-turbo-dev
sudo apt-get install cmake
sudo apt-get install gcc g++
```

Build and install the mjpg-streamer
```
cd ~
git clone https://github.com/jacksonliam/mjpg-streamer.git ~/mjpg-streamer
cd mjpg-streamer/mjpg-streamer-experimental
make
sudo make install
```

## Running the Application
Start the camera stream using mjpg-streamer

```
cd ~/touchUI
bash start_stream.sh
```

Start the node application
```
sudo node app.js
```

The application will be available at http://\<your rpi ip-address\>:3000
