# Emubox-CD

Emubox-CD is a custom Debian install CD. It comes packaged with EmulationStation, 
RetroArch, Dosbox, Scummvm, etc. The aim is for you to be able to repurpose old 
hardware (old laptops and desktops) as retro game/emulation machines. You burn
the Emubox-CD iso image to a CD or a USB flash drive, boot your old machine with
it, and install the custom Debian OS onto it, turning your creaky old Windows XP/
Vista machine into a multi-platform retro console of sorts.

Emubox-CD takes its inspiration from RetroPie, and makes use of several parts of 
RetroPie-Setup to do its work. While RetroPie-Setup can set up RetroPie on an existing
Ubuntu/Debian installation, Emubox-CD gives you a pre-packaged RetroPie install CD
that you can install from scratch on old hardware, replacing an old OS with a minimal
debian install customized for RetroArch, Dosbox and Scummvm.

RetroPie-Setup supports both x86/amd64 and Raspberry-Pi architectures. Emubox-CD
only supports amd64 for now, but that's only because I've only tested it on amd64
hardware. x86 support should be trivially easy. Emubox-CD will probably never
support Raspberry-Pi, because RetroPie already does a great job of doing just that.

# Building Emubox-CD images

You build Emubox-CD images on a Debian Stretch system like this:

- git clone https://github.com/ashwinm76/Emubox-CD.git
- cd Emubox-CD
- Create the emulationstation and emulationstation-data Debian packages as detailed in
  https://github.com/ashwinm76/EmulationStation
- Create the emubox Debian package as detailed in https://github.com/ashwinm76/Emubox
- Copy the created packages above to the local_packages directory
- build-simple-cdd -p emubox --logfile simple-cdd.log

An ISO image will be created in the images directory. Burn the image to a CD or
a USB flash drive, pop it into an old machine, boot the machine from it, and 
follow the Debian installation procedure that starts up.
