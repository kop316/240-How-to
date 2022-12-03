VCS  is  a  very  popular  and  powerful  simulation  program  for  a  variety of  simulation  languages,  including SystemVerilog. We shall use it as our primary simulation platform in 18-240 because it handles SystemVerilog quite well.  Should you continue on the digital design course track, you will undoubtedly use it again in at least 18-341, 18-447, and 18-725.  In addition to using VCS in lab / cluster (HH 1305), you can access VCS remotely on any of the ECE servers. However, VCS is a proprietary software that has been licensed to the ECE department. I haven't found a suitable open-sourced simulator that allows for all of the features we use in 18-240 and 18-341.

VCS works by compiling your SystemVerilog file into an executable, which you then run. You start by using a text editor to write your hardware description into a file (or files) with the extension `.sv`.  You can execute the file by running the simulation.  You can re-run the simulation by re-executing the file. But, if you make changes to your hardware description, **you must compile before running again.**

## Compiling your code
To compile:
```bash
vcs -sverilog [-otherflags] <filename>.sv
```

If you get sick of specifying -sverilog or other flags, you can place an alias
in your `.bashrc` file such as:
```bash
alias vcs240="vcs -sverilog -R +lint=all -debug_access+all"
```

And you can use `vcs240`

`vcs -help` shows you other available flags. Some useful ones are:
* -q &rarr; quiet mode, display less output
* -nc &rarr;even less output
* -xzcheck &rarr; look for x and z values in comparisons
* +lint=all &rarr; give me extra warnings when I do something stupid
* -debug &rarr; include extra information.  Necessary for GUI waveform viewer

Once you've successfully compiled (*make sure there are no errors!*) then an executable called `simv` will be created in your working directory.

## Running your simulation
To run:
```bash
./simv
````
To run in quiet mode (cut down on chatter, or if you're feeling grumpy)
```bash
./simv -q
```
To finish the simulation at a specified time, even if a `$finish` hasn’t been executed yet (useful for debugging code that hangs)
```bash
./simv -q +vcs+finish+[time]
```
To compile and run in one command:
```bash
vcs -sverilog -R <filename>.sv
```

# Next step
Next, let's see [how to compile a single module in a file with multiple modules](Simulating-a-single-module).
