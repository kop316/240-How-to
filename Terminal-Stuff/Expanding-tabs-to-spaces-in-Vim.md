You may have noticed that in our style guidelines, we expressly forbid the use of tabs in our code. Unfortunately, by default Vim puts in a tab whenever you press Tab on your keyboard, which as you may imagine gets annoying. Fortunately we can configure Vim to use spaces instead of tabs.

## Editing your `~/.vimrc`
Add the following lines:
```vim
set tabstop=4
set softtabstop=4
set shiftwidth=4
set expandtab
```

Note that the above will replace your tabs with **4** spaces. If you wish, you can change that number to the number of spaces you want.