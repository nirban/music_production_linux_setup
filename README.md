# music_production_linux_setup

# Install required dependencies if needed
sudo apt-get install apt-transport-https gpgv

# Remove legacy repos
sudo dpkg --purge kxstudio-repos-gcc5

# Download package file
wget https://launchpad.net/~kxstudio-debian/+archive/kxstudio/+files/kxstudio-repos_10.0.2_all.deb

# Install it
sudo dpkg -i kxstudio-repos_10.0.2_all.deb


#Install the production Softwares
sudo apt install ardour

sudo apt install zynaddsubfx-git

sudo apt install carla dexed-lv2 drumgizmo

sudo apt install avldrums.lv2

sudo apt install libfftw3-dev libaubio-dev libxml2-dev libcwiid-dev libjack-dev

sudo apt install qjackctl

sudo apt install pulseaudio-module-jack

sudo apt install libjack-jackd2-dev

sudo apt-get install musescore

#start qjackctl first as hardware as hw:CODEC,0 USB Audio{hw:1,0} I am using zoom g2.1u as audio interface


#install cst windows plugins using carla
sudo apt install carla-bridge-win32 carla-bridge-win64 carla-bridge-linux32 carla-bridge-wine32


sudo apt install vmpk

# This system was installed using small removable media
# (e.g. netinst, live or single CD). The matching "deb cdrom"
# entries were disabled at the end of the installation process.
# For information about how to configure apt package sources,
# see the sources.list(5) manual.
deb https://dl.winehq.org/wine-builds/ubuntu/ focal main
# deb-src https://dl.winehq.org/wine-builds/ubuntu/ focal main



# https://ubuntuhandbook.org/index.php/2021/05/wine-6-9-released-install-in-ubuntu-21-04-20-04/
sudo apt install --install-recommends winehq-staging
wine 'wineboot'
sudo apt install winetricks

# on manjaro with x11 this worked fine
winetricks vcrun2013 gdiplus urlmon
# on arch with wayland (amd) I needed
winetricks dxvk vcrun2013 gdiplus urlmon
# or else there was a gray overlay above the whole helix window

wine $PWD/Downloads/HelixNativev3.11Installer.exe

# install yabridge and follow its installation instructions
# linux reaper will find the vts3 version

sudo add-apt-repository ppa:ubuntustudio-ppa/ardour-backports
