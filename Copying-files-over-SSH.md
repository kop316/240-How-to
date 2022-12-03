The general workflow for coding assignments in 240 is:
1. Do the assignment
2. Hand in your files with `handin240`
3. Upload the generated PDF to Gradescope

That last step may be complicated if you're not working at a lab computer. The
PDF is located on an ECE machine, but you need to upload from your local
machine...the way we do that is using `scp` or `sshfs`.

## What is `scp`?
`scp`, or `secure copy` is a tool that allows us to copy files remotely. It is
functionally identical to `cp` (for the most part), with the added remote
functionality.

In 240, there will be times where you want to copy files from your local machine
to the ECE servers, and vice versa which is why you'll need to `scp`.

## How to use `scp`
Just like `cp`, the structure of an `scp` command is
```bash
scp path/to/sourcefile path/to/destfile
```
The thing to note is *whenever you want to specify a remote directory, you have
to add its address*.

For example, say you want to copy a file `foo.txt` from your local machine
(located at the folder `~/docs/foo.txt`) to your private directory on the Unix
machine (located at `unix.andrew.cmu.edu`):
```bash
scp ~/docs/foo.txt <andrewid>@unix.andrew.cmu.edu:~/private
```
A couple things to note:
1. You need to provide your login (your Andrew ID), then `@` followed by the
   hostname (`unix.andrew.cmu.edu`).
2. After the hostname, you **must** put a colon (`:`) followed by the path to
   the directory you want on remote. **Note that there is no space after the
   colon**.

In other words a *remote* path has the form
```
username@hostname:path/to/file
```

## Using SSH shortcuts with SCP
If you followed the guidance [for setting up SSH
shortcuts](Creating-SSH-shortcuts) then you can substitute everything
before the `:` with your shortcut.

So the remote path now becomes
```
ece:path/to/file
```
which is pretty neat.

## sshfs

On GNU/Linux and other Unix-like systems (and maybe OS X?), you can mount a remote filesystem you can ssh into with
`sshfs`. See [this guide](https://www.redhat.com/sysadmin/sshfs) for instructions.
