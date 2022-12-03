Home stretch! Thankfully this is the easiest step by far.

In order to properly use the tools in this class (namely VCS and Quartus), we
have to add these programs to your `PATH`.

1. First, **SSH into an ECE machine**. If you did the previous step in setup,
   this should be easy-peasy.
2. Edit your `~/.bash_profile` and add the following
   to the *top* of the file:
```
if [ -f $HOME/.bashrc ]; then
    source $HOME/.bashrc
fi
```
3. Edit your `~/.bashrc` and add the following:
```
source /afs/ece.cmu.edu/class/ece240/bin/setup_240
```

Beware that this setup script may conflict with other classes! If you have issues, ensure that no other class setup scripts are in your `.bashrc`

Note: As of F20, to ensure you don't have any permission errors when logging into Non-ECE machines, you will want to add a check to see if you are on the ECE machines:
```
if [[ -r /afs/ece.cmu.edu/class/ece240 ]]; then
  source /afs/ece.cmu.edu/class/ece240/bin/setup_240
  # Feel free to add any other ECE-specific setup commands here
fi
```
4. Exit out of the SSH session, and SSH into an ECE machine again. (Or run `source ~/.bashrc`)

If everything worked, you should be able to run all of the following:
```bash
which vcs
which quartus
which handin240
```
and they should print out the path to these programs. If any of them print
something along the lines of `/usr/bin/which: no ... in ...` then something
wasn't set up correctly.

# Next step
You're done! That should be all the setup you need for work in 240. I recommend
looking at the FAQ in case you run into other issues. If you ran into any
problems during setup, then ask a question on Piazza, or drop by office hours.
We're **always** here to help, and don't you forget that.
