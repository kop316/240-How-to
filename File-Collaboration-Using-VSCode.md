If you want to learn to set up and use Visual Studio code consult [[Using Visual Studio Code]]

# The "Live Share" Visual Studio Code Extension

Live Share is a 1st party Microsoft extension for Visual Studio Code, which allows files and directories to be worked on by multiple people at once. Think like sharing documents on Google Drive, where you can see the cursor of other people, with edits updated in real time. Furthermore, this extension allows terminals to be shared across users, leave comments throughout files, and more.

### This extension requires all users to sign in with a GitHub or Microsoft account.

![](https://i.imgur.com/WGVFP0A.png)

## Installing Live Share

1. Open VSCode, and navigate to the extensions tab.
2. Type in "live share" and the correct extension should be first on the list. Verify that the author is "Microsoft".
3. Click "Install" 
4. (This step requires being ssh'ed into the ECE servers) Since most work for 240 is done on the ECE servers, we need to make sure the extension can be used when SSH'ed into said servers. Make sure there's nothing in the search bar on the extensions tab, and you should see the list of extensions installed locally. Scroll down to live share and click the blue box with "Install in SSH: ece".  
5. Live Share should show up under the "SSH: ECE - INSTALLED" List

![](https://i.imgur.com/1ZYqWrK.png)

## Creating a Live Share session

1. To start a session, click on "Live Share" at the bottom of the VSCode Window. If you haven't logged into VSCode yet, it'll probably ask you to do so now. A session can also be started from the Live Share tab on the far left (the one that looks like an arrow going over a dot), by clicking the blue "Share" button. 
2. A notification will pop up saying a URL has been copied to your clipboard. That link will allow VSCode users to join your session. 

## Joining a Live Share session

Joining a session requires a join link, information on creating one can be found above. Clicking the join link will open a browser window. Click the VSCode icon, and the browser should ask to open VSCode. Allowing VSCode to be open MAY OR MAY NOT join the session. 

* If it DOES: Congrats, you can finally help your partner debug that datapath.

* If it DOES NOT: Copy the URL of the session that you want to join, and return to the VSCode window. Click on the "Live Share" tab, and click on the icon to the left of "Session Details". Paste the join URL into the textbook that appears, then press enter. This is the "manual" way of joining a session. 

* If you still have problems: Please post on Piazza, a TA or Student will most likely have experienced the same issue as you, and will be happy to help!

![How to manually join a session](https://i.imgur.com/czkWnSy.png)
 
## Stuff You Should Know

* Edits to files made in a live share session will only be saved for the user who created the session. 

* Using a shared terminal means the group is using the terminal of the user who created the session. All aliases, PATHs, extensions, and software from other users will NOT be used.
