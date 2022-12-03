This page explains how to simulate a single module in a file with multiple
modules.

The reason why this may be useful is because you may have a file that has
multiple testbenches/top-level modules. Running this simulation would cause
*all* of these testbenches to run, which will likely break things or lead to
nonsensical results. By following the steps here you no longer have to comment
out all but one of your top-level modules.

# Method 1

Run `vlogan` to "analyze" your file. This is a parsing step that is normally
executed by VCS, so you don't need to run `vlogan` if you’re going to run `vcs`
anyways.
```bash
vlogan -sverilog -nc <filename>.sv
```
If you have multiple files, you can include them all, such as:
```bash
vlogan -sverilog -nc <filename1>.sv <filename2>.sv
```
Run vcs, specifying the module name instead of a file name.
```bash
vcs -sverilog -nc <module_name>
```
Execute compiled simulation
```bash
./simv
```
# Method 2

Run vcs, specifying all files first, then the desired top module after `-top`:
```bash
vcs -sverilog -nc filename.sv -top module_name
```
As above, run your simulation (or add the `-R` flag to the line above):
```bash
./simv
```