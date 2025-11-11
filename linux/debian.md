# Debian tweaks

## Install Virtualbox Guest Additions in Debian based (debian/*buntu/mint) distribution

1. Install required libraries from terminal (`CTRL+ALT+T`)
   ```
   sudo apt update
   sudo apt install build-essential dkms linux-headers-$(uname -r)
   ```
2. Insert Guest Additions CD Image using VirtualBox manager (Devices -> Insert Guest Additions CD image)
3. Open the CD image
4. Run `autorun.sh` (Right click -> Run as program). Alternatively run from terminal
5. Reboot the machine `sudo reboot`
6. Confirm Guest additions by running from terminal `VboxService --version` or `lsmod | grep vboxguest`
7. Don't forget to eject the CD image (e.g. prior to creating a snapshot): `Right Click CD -> Remove Disk From Virtual Drive`
