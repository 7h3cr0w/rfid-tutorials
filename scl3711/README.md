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
After you pluged in the device you should see the device with `dmesg`

```bash
$ dmesg
....
[13976.015981] usb 2-1: new full-speed USB device number 24 using xhci_hcd
[13976.204647] usb 2-1: New USB device found, idVendor=04e6, idProduct=5591, bcdDevice= 2.07
[13976.204652] usb 2-1: New USB device strings: Mfr=1, Product=2, SerialNumber=0
[13976.204656] usb 2-1: Product: SCL3711-NFC&RW
[13976.204658] usb 2-1: Manufacturer: SCM Micro
[13976.223909] nfc: nfc_init: NFC Core ver 0.1
[13976.223949] NET: Registered protocol family 39
[13976.229570] usb 2-1: NFC: NXP PN533 firmware ver 2.7 now attached
[13976.232512] usbcore: registered new interface driver pn533_usb
```

or you could see it with `lsusb`
```bash
$ lsusb | grep SCM
Bus 002 Device 024: ID 04e6:5591 SCM Microsystems, Inc. SCL3711-NFC&RW
```
