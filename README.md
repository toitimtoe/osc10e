This contains source code for the 10th edition of
"Operating System Concepts" by Silberschatz/Galvin/Gagne.
Published by John Wiley & Sons 2018

Source files are organized by chapter. 

To download all files, enter

    git clone https://github.com/greggagne/OSC10e.git

which will clone this repository on your local machine.

-- Greg Gagne June 2018.

## Stupid steps to Configure shared folders for VirtualBox

1. On host machine, run `sudo apt-get install virtualbox-guest-additions-iso` to get
the file `/usr/share/virtualbox/VBoxGuestAdditions.iso`.
2. Set the ISO file above as an optical drive CD/DVD on the VM, by editing the "Settings/Storage"
from VirtualBox Manager.
3. On the VM, run `lsblk` to see whether the CD is available, and mount it.
For my case the CD is at `/dev/sr0` and `/dev/cdrom` is a link to it.
`sudo mount /dev/cdrom /media/cdrom`.
4. On the VM, go into `/media/cdrom` and run `sudo ./VBoxLinuxAdditions.run`.
5. Now the shared folder should be available.