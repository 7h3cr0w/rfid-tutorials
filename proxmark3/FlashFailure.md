# Fash Fail
```bash
$ ./pm3-flash-all 
[=] Waiting for Proxmark3 to appear...
[=] Session log /root/.proxmark3/log_20200106.txt
[+] About to use the following files:          
[+]     /root/git/proxmark3/client/../bootrom/obj/bootrom.elf          
[+]     /root/git/proxmark3/client/../armsrc/obj/fullimage.elf          
[+] Waiting for Proxmark3 to appear on /dev/ttyACM1           
.Found           
[+] Entering bootloader...           
[+] (Press and release the button only to abort )          
[+] Waiting for Proxmark3 to appear on /dev/ttyACM1           
........... Found           
[!!] ====================== OBS ! ===========================================           
[!!] Note: Your bootloader does not understand the new CMD_BL_VERSION command            
[!!] It is recommended that you first update your bootloader alone,            
[!!] reboot the Proxmark3 then only update the main firmware 
          
[=] Available memory on this board: UNKNOWN 
          
[!!] ====================== OBS ! ======================================           
[!!] Note: Your bootloader does not understand the new CHIP_INFO command            
[!!] It is recommended that you first update your bootloader alone,            
[!!] reboot the Proxmark3 then only update the main firmware 
          
[=] Permitted flash range: 0x00100000-0x00140000          
[+] Loading ELF file /root/git/proxmark3/client/../bootrom/obj/bootrom.elf           
[+] Loading usable ELF segments:          
[+]    0 : V 0x00100000 P 0x00100000 (0x00000200->0x00000200) [R X] @0x94          
[+]    1 : V 0x00200000 P 0x00100200 (0x00000dd0->0x00000dd0) [R X] @0x298          
          
[+] Loading ELF file /root/git/proxmark3/client/../armsrc/obj/fullimage.elf           
[+] Loading usable ELF segments:          
[+]    0 : V 0x00102000 P 0x00102000 (0x000402d8->0x000402d8) [R X] @0x94          
[!!] Error: PHDR is not contained in Flash          
[+] All done.       
```

So how it says you have to flash the bootloader first. You could do this with the proxmarktool itself.
```bash

```bash$ ./client/proxmark3 /dev/ttyACM1 --flash --unlock-bootloader --image bootrom/obj/bootrom.elf 
[=] Session log /root/.proxmark3/log_20200106.txt
[+] About to use the following file:          
[+]     bootrom/obj/bootrom.elf          
[+] Waiting for Proxmark3 to appear on /dev/ttyACM1           
.Found           
[+] Entering bootloader...           
[+] (Press and release the button only to abort )          
[+] Waiting for Proxmark3 to appear on /dev/ttyACM1           
........... Found           
[!!] ====================== OBS ! ===========================================           
[!!] Note: Your bootloader does not understand the new CMD_BL_VERSION command            
[!!] It is recommended that you first update your bootloader alone,            
[!!] reboot the Proxmark3 then only update the main firmware 
          
[=] Available memory on this board: UNKNOWN 
          
[!!] ====================== OBS ! ======================================           
[!!] Note: Your bootloader does not understand the new CHIP_INFO command            
[!!] It is recommended that you first update your bootloader alone,            
[!!] reboot the Proxmark3 then only update the main firmware 
          
[=] Permitted flash range: 0x00100000-0x00140000          
[+] Loading ELF file bootrom/obj/bootrom.elf           
[+] Loading usable ELF segments:          
[+]    0 : V 0x00100000 P 0x00100000 (0x00000200->0x00000200) [R X] @0x94          
[+]    1 : V 0x00200000 P 0x00100200 (0x00000dd0->0x00000dd0) [R X] @0x298          
          
          
[+] Flashing... 
          
[+] Writing segments for file: bootrom/obj/bootrom.elf          
[+]  0x00100000..0x001001ff [0x200 / 1 blocks]          
. OK           
[+]  0x00100200..0x00100fcf [0xdd0 / 7 blocks]          
....... OK           

          
[+] All done.  
```
After all now you can flash the whole system
```bash
$ ./pm3-flash-all 
[=] Waiting for Proxmark3 to appear...
[=] Session log /root/.proxmark3/log_20200106.txt
[+] About to use the following files:          
[+]     /root/git/proxmark3/client/../bootrom/obj/bootrom.elf          
[+]     /root/git/proxmark3/client/../armsrc/obj/fullimage.elf          
[+] Waiting for Proxmark3 to appear on /dev/ttyACM1           
.Found           
[+] Entering bootloader...           
[+] (Press and release the button only to abort )          
[+] Waiting for Proxmark3 to appear on /dev/ttyACM1           
........... Found           
[=] Available memory on this board: 512K bytes
          
[=] Permitted flash range: 0x00100000-0x00180000          
[+] Loading ELF file /root/git/proxmark3/client/../bootrom/obj/bootrom.elf           
[+] Loading usable ELF segments:          
[+]    0 : V 0x00100000 P 0x00100000 (0x00000200->0x00000200) [R X] @0x94          
[+]    1 : V 0x00200000 P 0x00100200 (0x00000dd0->0x00000dd0) [R X] @0x298          
          
[+] Loading ELF file /root/git/proxmark3/client/../armsrc/obj/fullimage.elf           
[+] Loading usable ELF segments:          
[+]    0 : V 0x00102000 P 0x00102000 (0x000402d8->0x000402d8) [R X] @0x94          
[+]    1 : V 0x00200000 P 0x001422d8 (0x00001460->0x00001460) [RW ] @0x4036c          
[=] Note: Extending previous segment from 0x402d8 to 0x41738 bytes          
          
          
[+] Flashing... 
          
[+] Writing segments for file: /root/git/proxmark3/client/../bootrom/obj/bootrom.elf          
[+]  0x00100000..0x001001ff [0x200 / 1 blocks]          
. OK           
[+]  0x00100200..0x00100fcf [0xdd0 / 7 blocks]          
....... OK           

          
[+] Writing segments for file: /root/git/proxmark3/client/../armsrc/obj/fullimage.elf          
[+]  0x00102000..0x00143737 [0x41738 / 524 blocks]          
..........................................................................................................................
..........................................................................................................................
..........................................................................................................................
..........................................................................................................................
.................................... OK           

          
[+] All done.           

Have a nice day!   
```

So now everything works fine and you can work again with your proxmark.
