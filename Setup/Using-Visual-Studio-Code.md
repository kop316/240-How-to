If you want to work on code on the ECE servers from off campus, see [Working Off Campus](Working-Off-Campus)

A big thank you to the student that posted these instructions! I'm sure it will
come in handy to anyone else that uses VS Code.

## A Set of Nice VSCode Shortcuts for Your Enjoyment...
https://code.visualstudio.com/shortcuts/keyboard-shortcuts-windows.pdf

## Using SFTP in VS Code
1. Download the SFTP extension. Go to [here](https://marketplace.visualstudio.com/items?itemName=Natizyskunk.sftp) to do that.
2. Create a folder in your local machine that you want to synchronize a
   directory on the ECE machines with.
3. Open that folder in VS Code, and hit Cmd + Shift + P on Mac or Control + Shift + P or F1 on Windows.
4. Type `sftp` and choose "SFTP: Config". A File named sftp.json will be created.
5. Save your `sftp.json` file as:
```json
{
    "name": "SOME NAME",
    "host": "HOST",
    "protocol": "sftp",
    "port": 22,
    "username": "ANDREWID",
    "remotePath": "YOUR_240_FOLDER",
    "uploadOnSave": true
}
```
Make sure you fill the `name`, `host`, `username`, and `remotePath` fields with
the correct values for your uses.

YOUR_240_FOLDER can be found by typing the command `pwd` while in the folder that you would like to use for 240.

6. Restart VSCode and navigate to the directory where the .vscode/sftp.json file you wrote above is contained within.
7. If you type Cmd + Shift + P on Mac or Control + Shift + P on Windows, a command palette should pop up. Type SFTP into the palette and you should see the options "SFTP: Sync Local -> Remote" and "SFTP: Sync Remote -> Local". Choose the first to copy your local files to your remote directory. Choose the second if you want to sync your remote files to your local directory. 
8. If you edit a file in your SFTP connected directory, the changes will automatically be written to the remote directory. Try it! In your local directory, using VSCode, create a test.txt file and write `hello world`. Now ssh into your ECE directory and go to the remote path you specified above. You should see a new file called test.txt! 

## Using Remote SSH on VS Code
1. Install extension: https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-ssh
2. Once that is installed, click the Remote Explorer icon on the side panel. A (empty) list of SSH targets should appear. 
3. Click the plus button next to the SSH TARGETS label to add a new target.
4. Type in your regular ssh command (`ssh <andrewID>@ece0XX.ece.local.cmu.edu`, where XX is some number between 00 and 31)
5. Select which SSH config file you want to update (you probably want to select the user one)
6. Select Linux as the remote platform and log in using your password
7. You should be logged into your account through VSCode.

Under the explorer, you can open a remote folder to see your remote directories through your sidebar. This will probably help you navigate through your files more easily. If you want to open a remote terminal, simply click the terminal tab and choose "new terminal". 

**Do note that there have been reports that this method causes bloat in your AFS directory due to VSCode server files.** If you find yourself unable to log in through VSCode, log in through some other means (such as your terminal). In your home directory, run the command `ls -a` to list all visible and hidden files. There should be a directory called `.vscode-server`. Deleting the directory using the command `rm -r .vscode-server` may help. **Make sure you are in your AFS home directory** before running the command. 

## Using SSHFS on VS Code
1. Install plug-in: https://marketplace.visualstudio.com/items?itemName=Kelvin.vscode-sshfs
2. Open the command pallet (Ctrl + Shift + p) and select "SSH FS: Create a SSH FS configuration"
3. At the "Create new Configuration" screen, enter in a name for this configuration.

![](https://i.imgur.com/loZ94dJ.jpg)

4. At this point, we want to fill out the following fields:

4.a Host: The server address (Where XX is some number between 00 and 31)

![](https://imgur.com/RkPpGQ6.jpg)

4.b Root: This just makes it easier for us to get to our own files more quickly

![](https://imgur.com/xvzccHe.jpg)

4.c Username: We use this for logging in

![](https://imgur.com/v3tT0eI.jpg)

4.d Password: Whenever you connect, you will be prompt for the SSH password. (Unadvised: You can actually enter your password here so you won't get prompted every time you connect, but keep in mind that it'll be stored in plaintext in the configuration)

![](https://imgur.com/bPKHrbV.jpg)

5. Save the configuration
6. To connect, open the command pallet (Ctrl + Shift + p) and select "SSH FS: Add as Workspace Folder"
7. When prompted, enter your password. Your workspace folder should be loaded on the left:
![](https://imgur.com/RvJgtU5.jpg)
8. Congratulations! You have connected to the ECE machine. Saving in VS Code should automatically sync the file to the server

## For Windows Users: Setting up a linux terminal
If you are on windows, and you want a better VS Code terminal, you should set up the Windows Subsystem for Linux and link it to your VS Code. After setting up SSH according to the guide, you can then use the terminal to run all the commands you need from one place, allowing you to neatly work with everything you need all within VS Code.

![](https://i.imgur.com/svErY7U.jpg)

Follow the instructions here to set it up: https://code.visualstudio.com/docs/remote/wsl