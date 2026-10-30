## -Almost-ready-to-run-GoodLuckOS
A GoodLuckOS backup/system file featuring more playable systems like N64, GG, SMS and much more (Not so stable but indeed possible to configure it).

## CONTEXT
Hello, this is my first time doing this, so basically, a friend of mine bought a R36S fake (GA36-MB) and I tried to help him to search for a custom OS, when I found out about GoodLuckOS, but one of the things that I noticed was the lack of emulators that even the EmueLec clone had, then I worked very hard to make them playable on GoodLuckOS
I used RaspberryPI 2 core library (extracted from RPi2.arm using 7-zip) for being compatible with Allwinner A33 (ARMv7 32-bit), changed the paths on APPS.puppy to bypass the Linux Ext4 partition "read-only" behavior, making it loads core from the retroarch HOME directory, then finally made everything run on HOME partition

## HOW TO INSTALL
1. **Download GoodLuckOS:** Choose the correct image version based on your console's screen panel display.
2. **Flash the Image:** Use software like BalenaEtcher or Rufus to flash the downloaded OS image onto your MicroSD card.
3. **Download the Fix:** Get the `HOME.zip` file containing the updated cores, infos, and path configurations.
4. **Extract Content:** Extract the contents of `HOME.zip` directly into the root of your card's `HOME` partition.
5. **Overwrite everything** if prompted.
6. **Boot and Play:** Insert the card back into your console, turn it on, have fun! :)


## HOW TO MODIFY
To add more emulators and systems that are available with the cores, you must put them on `APPS.PUPPY` like the following template
```ini
[ENTRY]
CATEGORY=Applications
NAME=Some Application
DESCRIPTION=This is an application!
ICON=/home/player/icons/application-icon.png
COMMAND=launch-the-application --some-flag

[ARCHIVE]
NAME=Playstation
Description=Sony Playstation
ENTRY_DIRECTORIES=/home/roms/psx
ENTRY_EXTENSIONS=bin;psx
ENTRY_ICONS_DIRECTORIES=/home/roms/psx/icons
DEFAULT_ICON=/usr/share/icons/psx.png
COMMAND=retroarch -L /usr/lib/libretro/pcsx_rearmed_libretro.so %s
```

To change the core paths in `RetroArch` (don't know why would you), you have to change the following lines:
```ini
"libretro_directory = "~/.config/retroarch/cores""
"libretro_info_path = "~/.config/retroarch/info"" 
```
in `RetroArch.cfg`
You must use `.so` cores and `.info` files to work properly
To add games just put them in the `HOME/roms/(game console)`
The icon folder works with the artboxes that can be downloaded via ScreenScraper (SkraperUI)

## DISCLAIMER
Almost all the games are on portuguese language.
Due to the lack of processing and power of Allwinner A33 many consoles may be unstable, those like PS1, PSP and N64 need more attention and effort to run properly, the only ones I tested so far are Nintendo 64 and Super Nintendo.
It may automatically boot with Kennel launcher, if not just run Kennel app on Puppy
I will also provide a separate ZIP file for the cores and another one for the stock OS image I used.

## Credits :
**CodeZombie (for developing and maintaining the goodluckOS core system and the Puppy frontend)**
**The Libretro & Lakka Teams (for providing the stable ARMv7/armhf RetroArch cores and core-info database)**
