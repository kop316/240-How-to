# On Mac (x86 Machines)
If you are on a Mac, you will not be able to run Quartus natively. Instead, you'll need to run a VM image that we will provide. The image runs Debian 9 and already has Quartus installed and ready to run.

**THE SUDO PASSWORD FOR THE IMAGE IS `341`**

_Note: If you are on any other platform, it would typically be better to just run Quartus natively._

1. Download the image

> You can either grab it at `/afs/ece/class/ece240/handout/vm/VM-image.tar.gz` or on Canvas under Modules > Labs

> The image is called `VM-image.tar.gz` and the associated documentation is called `VM-guide.pdf`
>
> You will need to unpack this tar to get the image

2. Install VMWare. 

> CMU offers a license [here](https://www.cmu.edu/computing/software/all/vmware/index.html)
> You might need to update the software, so check for updates after installing. 

3. Run VMWare

> Launch VMWare and load in the image
> Inside the VM, you may need to check some specific I/O settings so that your OS will pass your USB input to the VM
>> In your Mac settings, go to "System Preferences" > "Security and Privacy” > “Allow VMWare go access computer”
>> You may need to restart/remove the cable after enabling this if the VM still doesn't detect
> Also, you may need to VPN onto the campus to use the Quartus licence on the VM

4. Install Git (optional)
> Open a terminal in the VM and run the following commands:
`sudo apt-get update` and then `sudo apt-get install git`

If you have any questions about the VM or run into any issues, please post on Piazza, email the staff list, or come to OH! :)

_Note: If you have any issues on Mac, see the troubleshooting guide [here](https://github.com/CMU-18240/240-How-to/wiki/Quartus-VM-Troubles)_