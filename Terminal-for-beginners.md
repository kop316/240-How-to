If 18-240 is your first course that uses a terminal/command line interface (CLI) (or if you're a bit rusty) then you might need to brush up!

# Terminal

This guide assumes you have already set up a terminal environment. If you have not, then run through these instructions before reading this guide:
https://github.com/CMU-18240/240-How-to/wiki/Getting-a-terminal

Keep in mind that this is a very brief overview, most of the commands have a lot more functionality than what is briefly explained here.

* ls 
     * Shows a list of all files and directories in the current directory.
* cd [directory]
     * Changes the current directory to the new directory.
     * To return to the home directory run cd ~
     * To go back a directory from the current one use cd ..
* pwd 
     * Shows path to current directory
* cp [source] [dest]
     * Copies a file or directory from the source to the destination.
     * The source file should also include the path to that file.
     * The destination is the path location that you wish to copy the file to. The destination can also be a file path to a destination file.
     * Use the -r flag to copy directories.
* mv [source] [dest]
     * Moves a file or directory from the source to the destination.
     * The source file should also include the path to that file.
     * The destination is the path location that you wish to copy the file to. The destination can also be a file path to a destination file.
     * Use the -r flag to copy directories.
* rm [file/directory]
     * Removes files or directories.
     * Files or directories removed this way cannot be restored unless it is backed up in AFS. If you need to restore a file on AFS, consult: https://computing.cs.cmu.edu/help-support/afs-backup-restore.
     * Use the -r flag to remove the contents of a directory as well.
* mkdir [directory]
     * Makes a new directory in the current directory.
* touch [file-name]
     * Creates an empty file


# Vim/Emacs
Vim and Emacs are the two main text editors installed on the Andrew File System (AFS). It's important to know how to use at least one of these tools as you’ll be using it alot to edit code for programming assignments. If you’re looking for alternatives to these text editors or a more IDE experience, you may be interested in setting up SFTP with VScode or Sublime. To do so, you should consult these guides: 
* https://github.com/CMU-18240/240-How-to/wiki/Using-Visual-Studio-Code
* https://github.com/CMU-18240/240-How-to/wiki/Using-Sublime-Text-3

## Which to use?
We would encourage you to try both and see which you prefer. Most of this is a user preference.

## Vim:

Look [here](Using-Vim).

## Emacs:
* To use emacs to edit a file, run emacs [file-name]
     * This will open up the file in a GUI. It may take some time for emacs to open.
* Emacs functions like a normal text editor. You can use your mouse or arrow keys to navigate the file and have dedicated save, copy and paste buttons.
* If you are interested in learning the shortcuts, you can use this resource: http://faculty.kutztown.edu/spiegel/UnixWorkshop/emacs_commands_list.html 
