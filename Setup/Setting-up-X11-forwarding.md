X11 is a windowing system used primarily to display a GUI, which can be done
over SSH. Because this class makes extensive use of VCS's waveform viewer and
Quartus (both of which are GUIs), being able to use X11 forwarding when working
remotely can be extremely convenient.

Once you've set up X11 on your computer, turn on X11 forwarding using the `-Y`
option such that your SSH command is so:
```bash
ssh -Y $USERNAME@$HOST
```

Choose your operating system:
- [Mac OS](#mac-os)
- [GNU/Linux and other Unix like systems](#gnulinux-and-other-unix-like-systems)
- [Windows](#windows)

Also look at [speeding up your X11](#speeding-up-x11)

# Mac OS
Getting X11 setup is fairly straightforward--chances are you already have it
installed. You may already have XQuartz in `Applications/Utilities/XQuartz`. If
not, then you can [download it here](https://www.xquartz.org/) and install. Make
sure you restart your computer after installing.

# GNU/Linux and other Unix like systems
Most GNU/Linux Desktop Environments use X11/Wayland/Mir as a backend. Wayland/Mir have 
an X11 server for X11 forwarding. X11 servers require no additonal configuration.
If you are using a DE without the above backends, you likely are not 
reading this section, as you know what you are doing.

# Windows
There are many X11 servers for Windows out there due to a lack of official
support, so if you can find one that works for you then go for it. If you have no idea
where to start, we have guides for MobaXTerm and VcXsrv below. 

## MobaXTerm

MobaXTerm is probably the most straightforward X11 client to use. Open the link to their [download page](https://mobaxterm.mobatek.net/download.html), select the free version and install. 

Once MobaXTerm is installed, start it and select the session button on the top left of the window. Select SSH, type in the Remote host (`ece0xx.ece.local.cmu.edu`) and specify username (your andrewID). Double check the Advanced SSH settings and make sure X-11 Forwarding is checked. Press OK to create the user session. 

Once that is done, you should be able to select the ECE machine session from the sidebar. Double clicking it will start your SSH session with X-11 Forwarding enabled. 

## VcXsrv

Just open the link to their [download page](https://sourceforge.net/projects/vcxsrv/) and install. Once that is installed,
you'll want to edit your `/etc/environment` on WSL2 by adding the following line to it:
```
DISPLAY="localhost:0"
```
Save your changes and quit. If you're unsure how to use Vim, look [here](Using-Vim). 

When starting VcXsrv (it may be called XLaunch), first select whichever display setting you prefer. Then, select "Start no client" on the next screen. Click next and finish on the next few screens. 

That should be all you need to do to setup X11 forwarding on Windows. Don't
forget to restart your terminal before actually trying it out.

It is worth noting that **whenever you want to use X11 forwarding, you must open
VcXsrv before SSHing**.  A mild inconvenience, but that is the price us Windows
plebs must pay.

## Issues with WSL2 (for VcXsrv)
If you're running into issues with X11 forwarding in WSL2, this section may be useful to you. Many thanks to the student on Piazza for pointing this out!

Reference: https://stackoverflow.com/questions/61110603/how-to-set-up-working-x11-forwarding-on-wsl2

**This guide assumes you have WSL2 set up, [as per this page](https://github.com/edgykuma/240-How-to/wiki/Getting-a-terminal#windows)**.

### Unblock incoming connections to access the X11 server
1. Open Windows Security (Windows Defender) > Firewall & network protection
1. Open "Allow an app through firewall"
1. Scroll down until you see "VcXsrv windows xserver"
1. Make sure BOTH private and public are enabled (you might have to unlock the setting by clicking "Change settings")

### Fix forwarding on WSL2
1. Open `~/.bashrc` (on your WSL environment) and add the following lines to the bottom:
```
export DISPLAY=$(awk '/nameserver / {print $2; exit}' /etc/resolv.conf 2>/dev/null):0
export LIBGL_ALWAYS_INDIRECT=1
```
1. Save and exit
1. In your terminal, reload the bashrc with the command: 
```bash
source ~/.bashrc
```

### Start X11 server with specific settings
1. Run XLaunch (vcxsrv)
1. On the third page of the configuration, make sure to tick "Disable access control"
1. Finish setup and start the x server

# Speeding up X11 (for VcXsrv)
You may notice that opening those X11 windows on your laptop can be quite...*slow*. As you can imagine when working with GUIs like Quartus and the waveform viewer this can get frustrating. Try dragging signals around the waveform viewer and you'll see what I'm talking about. Thankfully this can be improved. Not fixed completely, but improved.

If you followed the steps in the [SSH shortcut setup](Creating-SSH-shortcuts) page then we'll just be adding a few lines to your `.ssh/config` file. In the block where you defined
```
Host cmu ece ece.campus
ForwardX11 yes
ForwardX11Trusted yes
User $ANDREWID
```

you'll want to add lines so that it looks like this:
```
Host cmu ece ece.campus
ForwardX11 yes
ForwardX11Trusted yes
User $ANDREWID
Cipher chacha20-poly1305@openssh.com
Compression yes
```

Save and quit. I find that these significantly speed up the X11 stuff for me,
but like a lot of things computers, your mileage may vary.

# Next step
Now we can [set up our SSH shortcuts](Creating-SSH-shortcuts).
