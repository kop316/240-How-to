# Installing quartus
1. Download [Quartus Prime Lite Edition](https://fpgasoftware.intel.com/20.1/?edition=lite&platform=windows). You will need to create an Intel Account. Clicking the download button will lead you to create an account.

> Select "Quartus Prime (includes Nios II EDS)" and "Cyclone V device support" (Make sure to select "Lite" or "Standard Edition):
>
> (NOTE: This website is kinda wonky, you may need to disable adblock to download)

![](https://i.imgur.com/VsrJiY9.jpg)


2. Un-tar (You may need [7-zip](https://www.7-zip.org/) for this) and install Quartus

![](https://i.imgur.com/d6h2HxQ.png)

3. Install Device Drivers (so that Quartus is compatible with your board):

> Open"Device Installer" in the Windows Search Bar

![](https://i.imgur.com/CL7pa3w.png)

> Keep clicking next until you reach this screen. Then, select the directory containing the downloaded Cyclone V driver files (.qdz):

![](https://i.imgur.com/wAKzfEF.png)

4. Install the USB Drivers (so that Quartus can Program your board):

> Run DPInst.exe, inside your Quartus installation (See directory below):

![](https://i.imgur.com/1Kh15R6.jpg)

> On success, you should see this: 
>
> (NOTE: Certain drivers may fail to install, but we are just looking for the Altera USB-Blaster Device Driver Package)
>
> If you are having driver troubles, try [this](https://www.quora.com/If-Windows-found-driver-software-for-your-device-but-encountered-an-error-while-attempting-to-install-it-how-do-you-fix-it) link. NOTE: Make sure to restart after so that you re-enable device signature enforcement!
>
> If this is giving you even more troubles, you may have to [disable SecureBoot](https://fossbytes.com/enable-disable-secure-boot-windows-8-10/)
>
> If this is giving you even even more troubles, you'll need to [disable Driver Signature Enforcement](https://windowsreport.com/driver-signature-enforcement-windows-10/). 
>
> FOR SECURITY PURPOSES, please restart you computer and revert the SecureBoot and driver changes after you've finished installing the drivers.
>
> **NOTE: YOUR DRIVER ISSUES ARE LIKELY DUE TO THE FACT THAT ALTERA _DOESN'T SIGN THEIR DRIVERS_**

![](https://i.imgur.com/k19euPM.jpg)

> Alternatively, you can go to the [Terrasic website](http://www.terasic.com.tw/wiki/Altera_USB_Blaster_Driver_Installation_Instructions) to grab the drivers for USB Blaster ii

# Checking that everything works

If everything worked (and your device is powered on and plugged in), you should be able to following steps to see the USB-Blaster option.

![](https://i.imgur.com/Or96SfU.png)
![](https://i.imgur.com/zQ1gJRr.png)
![](https://i.imgur.com/16eIcE1.png)