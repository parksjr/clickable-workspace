# Ubuntu Touch App Development Workspace for Windows
## Prerequisites
* Vagrant
* VirtualBox
  * you can use other VM providers, usb device forwarding configuration will need to be modified per provider specifications.
* Supported device with Ubuntu Touch, connected via USB
  * Nexus 5 (hammerhead)
  * OnPlus One (bacon)
## Setup
* clone this repo
* plug in Ubuntu phone via usb
* If your device is not listed above in the prerequisites, you can add it like so:
  * run ```VBoxManage.exe list usbhost```
  * copy VendorId and ProductId of the connected phone
  * Open the VagrantFile in this repo, and replace the ```--vendorid``` and ```--productid``` values with your own (line 9).
* run ```vagrant up```
## Development
Use putty to ```vagrant ssh``` into the vagrant box and start clickable development. The apps folder is shared between host and guest. How I do it is generate clickable app template on the guest /home/vagrant/apps, alter any files i need using IDE on the host. Build and test run using clickable on the guest. The app should pop up on the connected phone.
## Notes
* The apps folder is ignored by git, essentially each app will have its own folder within, and should be its own git repo.
* This is obviously a bit much (a virtual machine to run click dev which uses docker containers... on a Windows host?? *puke*) I know, I know. 