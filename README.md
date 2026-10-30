# -Almost-ready-to-run-GoodLuckOS
A GoodLuckOS backup/system with more playable system like N64, GG, SMS and much more (Not so stable but indeed possible to configure it).
CONTEXT
Hello, its my first time doing this, so basically, a friend of mine bought a R36S fake (GA36-MB) and I tried to help him to search for a custom OS, when I found out about GoodLuckOS, but one of the things that I noticed was the lack of emulators that even the EmueLec clone had, then I worked very hard to make them playable on GoodLuckOS
HOW IT WERE DONE
I used RaspberryPI 2 core library for being compatible with Allwinner A33 (Armeabi-v7)
HOW IT WORKS
To modify the core paths in retroarch (don't know why you would), you have to change the lines:
"libretro_directory = "/.config/retroarch/cores"
"libretro_info_path = "~/.config/retroarch/info"
WARNING! 
