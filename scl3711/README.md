# SCL3711 with Kali
This short tutorial is to setup SCL 3711 and read or write RFID Cards with NFC-TOOL under KALI.
![SDC3711](https://github.com/7h3cr0w/rfid-tutorials/blob/master/scl3711/scm3711.jpg)

## Download the Driver
Install the driver from [scm-pc-card](https://scm-pc-card.de/index.php?page=download&function=show_downloads&lang=en&product_id=610)

```bash
tar xzvf scl3711_-_linux_64-bit_driver.gz
```

```bash
cd sclgeneric_2.09_linux_64bit/
./install.sh
```

## Find the device
After connecting the device and typing `lsusb` the device should 

```bash
$ lsusb | grep SCM
Bus 002 Device 024: ID 04e6:5591 SCM Microsystems, Inc. SCL3711-NFC&RW
```
