## General Usage
Vim is a very powerful editor that is installed on nearly every Unix-like machine you log into. This makes it a good tool to learn because it is so portable. Several good tutorials exist, including `https://www.openvim.com/`, and the VimTutor (run `vimtutor`).

## How do I exit vim?
See [here](https://stackoverflow.com/questions/11828270/how-do-i-exit-vim) and [here](https://github.com/hakluke/how-to-exit-vim)

## Other Tips and Tricks
* To use vim to edit a file, run vim [file-name]
     * This will open up the file in the terminal.
* The default mode of vim is normal mode. In this mode, you cannot edit the file.
* To edit the file, press the i key. This puts you into insert mode, where you can edit the file as normal.
     * To return to normal mode, press the Esc key.
* To navigate the file,  use the hjkl keys or the arrow keys.
* To save, in normal mode, type :w and press enter.
* To exit the file, in normal mode, type :q and press enter.
     * You can both save and exit at the same type by typing :wq and pressing enter in normal mode
With this, you know how to use vim at a very basic level. To find more commands, you can either use this resource: https://vim.rtorr.com/ or use google.
* [[Expanding tabs to spaces in Vim]]

## Syntax Highlighting
Due to the old Vim version on the ECE machines (7.4), Vim does not have syntax highlighting for SystemVerilog. We can add this functionality by executing the following commands:
1. Create the required directories:

`mkdir --parents ~/.vim/syntax ~/.vim/ftdetect`

2. Copy all of the needed files into these folders:

`cp /afs/ece.cmu.edu/class/ece240/lib/sverilog-vim/verilog.vim ~/.vim/syntax/`

`cp /afs/ece.cmu.edu/class/ece240/lib/sverilog-vim/systemverilog.vim ~/.vim/syntax/`

`cp /afs/ece.cmu.edu/class/ece240/lib/sverilog-vim/verilog-detect.vim ~/.vim/ftdetect/`

Credit to Michael Crotty for making these files!
