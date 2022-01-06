# ROM

Read [LIMITATIONS](LIMITATIONS.md) before every flashing!!

## Install adb/fastboot

`choco install adb -y` / `yay adb`

## New phone

If you just bought your new phone, here are things you might need to do. Example
for Poco F3.

### Unlock bootloader

You'll most probably need to
[unlock the bootloader](https://4pda.to/forum/index.php?showtopic=721838&st=14360#entry63359408)
to install custom ROM and recovery.

* Use sim-card instead of Wi-Fi
* Activate menu for developers -> status mi unlock -> login
* ...
* ... waiting ...
* ...
* Launch MiFlashUnlock -> login -> phone into fastboot mode (voldown+power until
vibration) -> unlock. You'll probably need drivers if your phone can't be seen
in fastboot mode.

### Backup IMEI, initial ROM, etc

TODO: write info here.

## Flash fresh firmware / rom / etc

### Flash fresh MIUI boot twrp

First thing to do is update official MIUI, so you'll have updated firmware, etc.
Source from [4pda](https://4pda.to/forum/index.php?showtopic=1023071&st=1840#Spoil-109050881-13).

* Download zip with MIUI fastboot — [spoiler for roms -> official -> global](https://4pda.to/forum/index.php?showtopic=1019227)
* Extract -> Edit `flash_all_except_storage.bat` -> Remove `fastboot reboot`
* Download MiFlash
* Install drivers untill it shut up on startup. Maybe helps QDLoader HS-USB Driver 32/64-bit
* F3 Fastboot -> MiFlash -> without reboot make `fastboot boot twrp.img`

### Flash ROM / recovery TWRP

* TWRP -> Wipe -> Format Data -> yes
* TWRP -> Advanced -> Adb sideload -> `adb sideload arrowos.zip`
* Somehow copy boot.img (TWRP); DFE; Magisk; NikGapps into internal storage
* TWRP -> Advanced -> Install recovery ramdisk
* Reboot -> Recovery
* Install 1-by-1: DFE; Magisk; NikGapps Core (Version S)
* TWRP -> Wipe -> Format Data -> yes
* Reboot -> Recovery (just in case) -> Reboot -> System

### First to install apps

Gboard, Nova, KeepassDX, Nextcloud, Fennec
