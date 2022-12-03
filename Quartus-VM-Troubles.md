If you are having trouble using the programmer on the VM, these solutions might help you a bit...

# Run Quartus as root

1. Close out of any open instances of Quartus
2. Open up the terminal in the VM
3. Run`su` to switch your terminal to `root`. The password is `341`

4. Run `/home/ece341/intelFPGA_lite/18.0/quartus/bin/quartus`
5. Launch Quartus and attempt to program your board

# Restart the jtag server

Sometimes, the jtag server will hang and become irresponsive. (If running the command that lists the jtag devices hangs, then this is your problem)

Nevertheless, running `sudo killall -9 jtagd` should fix this

> Note: You theoretically shouldn't need to exit Quartus to do this