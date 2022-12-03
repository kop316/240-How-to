If you've already gone through the tutorials on Canvas, I'm sure you're already
sick of typing out the entire SSH command. This page will help you stop doing
that.

## About SSH shortcuts
Inside of `~/.ssh/config` (if you already have the file), we can define SSH
"shortcuts" so instead of typing, say:
```bash
ssh -Y acarnegie@foo.andrew.cmu.edu
```
you can simply do
```bash
ssh cmu
```
Cool, right? Let's see how we can set that up.

## Creating a `.ssh` folder
If you do not have a `.ssh` folder, then you'll have to make one:
```bash
mkdir ~/.ssh
```
If you need to check if you have said folder, then run
```bash
ls ~/.ssh
```

## Modifying your SSH config
We will be adding the following block of text to our `~/.ssh/config`.  DO NOT SIMPLY COPY AND PASTE THIS BLOCK.  See the notes below, as you have to customize it with favorite machine and your own Andrew ID.
```
Host cmu
Hostname unix.andrew.cmu.edu

Host ece
ProxyCommand ssh -W %h:%p cmu

Host ece ece.campus
Hostname ece0XX.ece.local.cmu.edu

Host cmu ece ece.campus
ForwardX11 yes
ForwardX11Trusted yes
User $ANDREWID
```
Where the `XX` in `ece0XX...` is a number between `00` and `31`, inclusive.
These are the available ECE machines you can SSH into, and `$ANDREWID` is just
your Andrew ID. Note that you should not include the leading `$`.

So let's make these edits.
1. Open your config by typing in your Unix terminal: `vim ~/.ssh/config`.
2. At the top of your file, copy the previous textbox's contents and paste. You
   may have trouble pasting into Vim, so if it comes down to it you should
   probably just type it in manually. Don't whine, the effort here will save you
   countless seconds typing in an SSH hostname.
3. In the previous step, don't forget to replace `XX` with a number between `00`
   and `31`, and also `$ANDREWID` with your own!
4. Save and quit.

You should now be able to use your SSH shortcuts. Note that these shortcuts
**already have X11 forwarding enabled**, so no need to use the `-Y` flag.

## Checking if it works
```bash
ssh cmu
```
Will allow you to SSH into the Unix machines. Note that **these are not the same
as the ECE machines**! They do not have the tools you need to compile, simulate,
and synthesize your code in 240!

```bash
ssh ece
```
Will actually SSH into the ECE machines. Note that these machines are only available on the CMU domain, so if you are off campus, you must [VPN in](Working-Off-Campus).

Also note that the ECE machines are shared machines, so you may want to create aliases to a few of the machines if one us busy.

## Resolving permission errors on .ssh/config
You may run into a problem where trying to SSH gives an error like
```
Bad owner or permissions on...
```

To solve this, you can try taking ownership of the file:
```bash
sudo chown $USER ~/.ssh/config
```
(where `$USER` is your username in your terminal)

Or, you can give yourself read/write permissions:
```bash
chmod 600 ~/.ssh/config
```

Reference: https://serverfault.com/questions/253313/ssh-returns-bad-owner-or-permissions-on-ssh-config

# Next step
Finally, the last step for setting up your environment is [resolving your paths
on the ECE machines](Setting-up-18240-paths).
