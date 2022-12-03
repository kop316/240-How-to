If your computer's locale isn't set to the US, you may run into error messages
that look something like
```
bin/sh: warning: setlocale: LC_ALL: cannot change locale (C.UTF-8)
```

This is an issue with your own locale settings (not with the ECE or Unix
server's). It should be easily fixed by installing the locales.

**On your local computer** (not SSH'd):
1. Assuming a Debian based system, run the command below. You should get a rather bright pink screen.
```bash
sudo dpkg-reconfigure locales
```

2. *Using the arrow keys*, go down until you find `en_US.UTF-8 UTF-8`. Highlight that and hit Spacebar.
3. Hit Enter.

4. Highlight `en_US.UTF-8` again and hit Enter.

That should install the necessary locale stuff, and remove the errors from earlier.


***
If this doesn't work go to your bashrc on your remote connection and add this line:
```bash
export LC_ALL=C
```
then exit out of your bashrc and type
```bash
source ~/.bashrc
```