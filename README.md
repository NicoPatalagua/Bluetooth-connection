# Bluetooth-connection
# Bluetooth 🌐
_Bluetooth is a **wireless** technology standard managed by the **Bluetooth Special Interest Group** (SIG) and with **IEEE 802.15.1** standard. Used for the exchange of data between fixed and mobile devices over short distances using UHF radio waves of short wavelength of 2,400 to 2,485 GHz, widely used to build **personal area networks** (PAN)._

# Basic steps 📖
These instructions allow you to communicate the two raspberry pi3, through bluetooth technology.

### 1. Mac Address 📋
 We have to know the bluetooth addresses or the mac address of each device.
 
_For this we go to the terminal and type the command_

```
hciconfig
```
_For my example the MAC of my first raspberry will be `B8: 27: EB: 6A: E1: BD` and the second raspberry will be `B8: 27: EB: FC: 72: 30`._

### 2.RFCOMM ⚙️
Now we must configure the `rfcomm.com` file.
 
_For that, we use the command:_

```
sudo nano /etc/bluetooth/rfcomm.conf
```
_After executing this command, we will modify the file as follows (On each device):_

```
rfcomm1{
        bind yes;
        device MAC;
        channel 1;
        comment "Bluetooth"  
    }
```

⚠**NOTE:** _Where it says MAC, we will replace with the address we found earlier._

## Install library 📂
On each device, uses Bluez for Linux. We are going to install the library that will allow us serial communication, by the   following command in the terminal
```
sudo apt-get install bluez python-bluez
```

⚠**NOTE:** _Taken from [Rfcomm](https://people.csail.mit.edu/albert/bluez-intro/x232.html) y [PyBluez](https://people.csail.mit.edu/albert/bluez-intro/c212.html)_
  
## Scripts 📄

We need to use the two scripts in this repository, one is going to pretend to be a gas station and the other will be a car.

⚠**NOTE:** _Run the Station script first and then the car script._

### 1. Station ⛽

_The script execution command of the station is:_

```
python GasStation.py
```

### 2. Car 🚗
_The script execution command of the car is:_

```
python CarGasStation.py
```

## Finally 📦

_After this, we can modify the scripts according to what we need. Here we can configure the connection form and even the protocols_

## Author ✒️

* **Nico Patalagua** - *Repository* - [Github](https://github.com/NicoPatalagua)

## If you liked this repostory 🎁
* Share it 📢
* Invite me a beer 🍺  
* Improve it 🤓.

---
## By 📌
[NicoPatalagua](https://www.instagram.com/nicopatalagua/) 😎
