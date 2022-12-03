The work you do in this class (and many of the ECE/CS classes at CMU) will involve a (bash) terminal one way or another. If you don't have a working terminal environment, this page will serve to help you with that.

Before we begin, go to the setup for your operating system:
- [Mac OS](#mac-os)
- [GNU/Linux and other Unix-like systems](#gnulinux-and-other-unix-like-systems)
- [Windows](#windows)

# Mac OS
As Mac OS is already a POSIX compliant system, you should already have a terminal emulator ready to go at `Applications/Utilities/Terminal` (or type `terminal` into Spotlight to save some time).

The builtin terminal emulator is perfectly sufficient for your needs, but if you want to configure it more to your liking there are other third-party terminal emulator out there you may use. One option is [iTerm2](https://www.iterm2.com/), but as with everything YMMV.

# GNU/Linux and other Unix-like systems
Assuming you are using a Desktop environment, you already have a perfectly functional terminal emulator. Simply search for `terminal` in your application menu and the first result should be the right one.

If not, you are using the terminal already and don't need this part of the guide.

# Windows
In the past, getting a bash environment on Windows can be...troublesome. Thankfully Microsoft has addressed this and added a Windows Subsystem for Linux (WSL).

The [official guide linked here](https://docs.microsoft.com/en-us/windows/wsl/install-win10) is fairly comprehensive, and should get WSL up and running on your machine with any custom configurations you might be interested in. 

If you're not too familiar with Linux/WSL, you probably just want to install WSL 2 with the default Linux distribution Ubuntu. Here's an (abridged) guide:
1. Hit the "Windows" Key, type `cmd` and open "Windows Command Prompt"
2. Type ```wsl --install``` into the Command Prompt and press enter.
3. Restart your computer.
4. Upon restart, your computer might automatically have an Ubuntu window open. If not, open your command prompt again and type `wsl`
5. Configure your Ubuntu username and password. Once that is done you should have a fully-functioning terminal!

That should be all you need to get a Unix terminal running on Windows. The next time you need to access the terminal, open your command prompt and type `wsl`.

# Next step
Now that you have a terminal emulator, we can go ahead and [set up X11 forwarding](Setting-up-X11-forwarding).
