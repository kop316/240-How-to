When working with a lab partner, you may find that you'd like to share files
with them. There are multiple ways to do this, with *varying* effectiveness. You
could use something like Google Drive, but that's kinda dumb. But wait, **don't
we all use the ECE machines**? *Can't we configure a way to share files on
there?* The answer is _yes_!

## What is `fs`?
`fs` is a way we can control access to folders and files in AFS (**A**ndrew
**F**ile **S**ystem), which is the file system we use at CMU. Using `fs` we can
allow some users/groups access to certain folders, and deny the rest. Fun fact:
your `private` directory has `fs` configured to only give you (and
administrators) access!

If you're curious, a longer guide on how to use `fs` is found
[here](https://userguide.its.cit.cmu.edu/services/data-storage/afs-access-control-and-security/).

## How to use `fs` to share files with another student
The first thing you want to do is create a public folder to house all of your
240 lab files. The reason for this is because **if you put your lab files in
`private`, then your lab partner can't get to it!** You can name it whatever you
want, but just for example:
```bash
mkdir ~/18240_lab
cd ~/18240_lab
```
Now create a folder for the lab you're working on.
```bash
mkdir labX
cd labX
```
Once you're in that folder, then you can simply use the following commands to
give your lab partner access.
```bash
fs sa . <labpartner-id> write
fs sa . <labpartner-id>@andrew.cmu.edu write
fs sa . system:anyuser none
fs sa . system:ece none
fs sa . system:authuser none
```
This will give your lab partner (replace `<labpartner-id>` with their Andrew ID)
read and write access to that `labX` folder, and deny any other user access.

Note that the above will configure the permissions for the **current** folder.
*Do not run the commands in some place like your `private` folder!* Failure to
lock down your private files **is an academic integrity violation**!

To confirm that it works, run
```bash
fs la .
```
and you should get something like
```
Access list for . is
Normal rights:
    system:administrators rlidwka
    <your-id> rlidwka
    <partner-id> rlidwk
    <partner-id>@andrew.cmu.edu rlidwk
```

Now you can get the absolute path to your lab folder by typing
```bash
readlink -m ~/18240_lab/labX
```
which will give you an absolute path, which you can give your partner and they
can `cd` into it to access the lab files.

## Sharing files in an existing folder with subfolders
You may already have a directory that has many folders in it. Unfortunately the
last section only configures the current working folder. Thankfully there is a
way around this.

**Make sure you** `cd` **into your lab folder first**. Then run
```bash
find -type d -print0 | xargs -i --null fs sa {} <labpartner-id> rlidwk
```
to recursively configure permissions for the current folder and every subfolder
within.
