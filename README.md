# proxmark3 rdv 4.0
## Setup your proxmark3 on KALI
- Kali version 2019.4
-
[CheatSheets](./CheatSheet.md)

### Remove ModemManager
The ModemManager could brik your proxmark so stop the manager first or better if you do not need him remove him forever.

#### Kill the ModemManager:
`killall ModemManager`

#### Remove the ModemManager:
`apt remove ModemManger`



### Download repository

### Build Toolssudo 

Install the main Tools for building the Tools first:
`sudo apt install git build-essential libreadline5 libreadline-dev gcc-arm-none-eabi libusb-0.1-4 libusb-dev libqt4-dev ncurses-dev perl pkg-config libpcsclite-dev pcsc`

