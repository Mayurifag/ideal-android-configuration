# Limitations

The following are some known limitations due to either the design nature of
Virtual A/B or a problem with ROM themselves. Please read carefully :

1) You cannot format data after flashing a ROM zip (Limitation of Virtual A/B).
If you want to format, then reboot recovery after flashing ROM. Additionally, if
you are encrypted, the newly flashed ROM must be able to decrypt your device. If
not, then you have to format data before flashing the ROM It appears, you can
actually format data after reboot even if the new ROM cannot decrypt.

2) You can flash only one ROM in one boot. If you wanna flash another ROM, you
must boot to system once. This is again a limitation of Virtual A/B.

3) Once you have rebooted after flashing a ROM, you cannot write to the data
partition until you boot successfully to the new ROM. Android seals the data
partition after a ROM flash to prevent any accidental brick since the newly
flashed ROM is actually stored in /data. Only data format is allowed in this
case. Once you successfully boot to the new ROM, your storage becomes ready for
writing again.

4) Ideally, after flashing a new ROM, you should only need to wipe your data
rather than format. But, due to a problem in the device trees current ROMs are
using, you will have to format data if you are currently on miui and want to
switch to a custom ROM. Specifically, the roms need this commit and to set
vendor security patch level to fix this issue. Switching between custom ROMs
should not need format, except for hentai OS.

5) If you are currently on hentai OS, then before using TWRP, you must flash
vendor_boot from the link provided in every hentai OS release. Otherwise, you
will get black screen. This is only needed when you boot to TWRP for the first
time. Do not repeat this step again. Also, do not try this with beta version of
the ROM. Use it only with stable.

6) If you reboot to older slot after flashing new ROM, the new ROM will be
cancelled and you will have to reflash again. This is because of how Virtual
A/B works.

7) If you must flash magisk via recovery (it's not recommended now), please
uncheck "Inject TWRP after install" else TWRP will remove magisk.

8) Do not flash magisk after flashing a ROM before reboot. Magisk's zip detects
slot in a different way that will cause issues.

9) Backuptool (used to persist magisk and gapps across ROM updates) will also
not work in recovery due to A/B. You will have to flash gapps (or any other
zips) everytime after flashing a ROM.
