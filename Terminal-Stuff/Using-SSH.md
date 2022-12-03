In order to work remotely (and access the tools used in 240 when outside of
lab), we can use `ssh`. Doing so allows us to work on the ECE machines without
physically being there.

Because tools like `vcs` and `quartus` are only licensed on the ECE machines,
you can only use these by doing either of the following:
1. Log into a machine in the HH1305 lab
2. SSH onto an ECE machine

This page is geared to help you with the latter solution.

## SSHing into an ECE machine
### Creating aliases
Follow the guidance on [this page](Creating-SSH-shortcuts) to set up SSH
shortcuts. Then to SSH all you have to do is type
```bash
ssh ece
```
If you are on-campus wifi or VPN, then you can also type
```bash
ssh ece.campus
```
To skip having to type your password twice.

### The manual way
You should be able to SSH into the ECE machines with
```bash
ssh -Y <andrewid>@ece0XX.ece.local.cmu.edu
```
Where `<andrewid>` is your Andrew ID, and `XX` in `ece0XX` is any number between
`00` and `31`, inclusive.

If you are off campus, you must use a VPN to access the numbered ECE servers [This page](Working-Off-Campus) should have the instructions you need.