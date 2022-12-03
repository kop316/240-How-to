handin240 is a handin utility tool for 18240 assignments. Meant to streamline 
student workflow with respect to code submissions with the intent of removing 
Autolab from the flow entirely, as well as make the lives of the (best) TAs 
easier.

Written in Python, updated to Python3

If you have any problems/questions *please read this in its entirety first*. If
you still have problems/questions, then please post on Piazza.

## Usage
Before you can use this script, [you must perform some setup](home#setting-up-your-environment)

After setup, simply run
```bash
init_handin240
```
and you'll have installed all the necessary dependencies for the handin script.

### Using the handin script
To actually perform a handin, first make sure you are in a folder that has **all** of the files you need to hand in for the homework. Then run
```bash
handin240 hwNum
```
Where `hwNum` is the number of the homework you are trying to submit. For example, to submit hw1 you would type into your terminal
```bash
handin240 hw1
```

You may find it helpful to see what else the script can do:
```bash
handin240 -h
```

The handin script will do the following:
1. Checks to see that the file exists.
2. If necessary, checks to see that the file compiles.
3. Submits all files to your handin directory in AFS.
4. Creates a PDF of your code **that you must submit to Gradescope**. The name
   of this PDF will be `hwNum_code.pdf`.

To reiterate: **DO NOT FORGET TO SUBMIT THE PDF TO GRADESCOPE!** Remember that
homework assignments have both code *and* a written component. Don't forget, or
you won't receive credit for your work! You'll need to either `scp` or use some
other file transfer program to copy the PDF to your machine, so that you can
submit to Gradescope.

### Handing in bad files
You may notice that if you try to hand in code that either does not exist, or
does not compile, the handin aborts. This is intentional. As per course policy:
**code that does not compile will receive zero points**. No exceptions.

Of course, sometimes you simply don't have time to finish all of an assignment.
We get it, it happens all too often. If you want to handin an incomplete
assignment then run the script with the `-f` flag:
```bash
handin240 hwNum -f
```
and this will force the handin with incomplete files.

Additionally, you may opt to skip the compilation step by using the `-s` option.
This is best used if you had just compiled the files on your own before
attempting to submit. If you skipped the compilation step and your code doesn't
compile, again **you will get a zero**.

Again, **do not forget to submit the PDF to Gradescope**!
