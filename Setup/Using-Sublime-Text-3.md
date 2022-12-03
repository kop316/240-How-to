If you want to work on code on the ECE servers from off campus, see [Working Off Campus](Working-Off-Campus)

You can download Sublime Text 3 from here: https://www.sublimetext.com/3

You now need Package Control. Follow the directions here: https://packagecontrol.io/installation

Then you want SFTP: https://wbond.net/sublime_packages/sftp/installation

You should set up the ECE server as a profile. Go to `File > SFTP > Setup Server`. Save it with an appropriate name (I use "cmuece") and then fill out the fields in the text file.

I'll put my own here as an example. Note that you need to change the `host`, `remote_path` and `user` for this to work.

```
{
    // The tab key will cycle through the settings when first created
    // Visit http://wbond.net/sublime_packages/sftp/settings for help

    // sftp, ftp or ftps
    "type": "sftp",
    "host": "eceXXX.campus.ece.cmu.local",
    "user": "acarnegie",
    "port": "22",

    "remote_path": "/afs/ece/usr/acarnegie/Private/",
    "connect_timeout": 10,
    "keepalive": 120,

    "remote_encoding": "utf-8",
    "save_before_upload": true,
    "upload_on_save": true,
    "sync_same_age": true,
    "sync_down_on_open": true,
}
```

Now to use the server. Go to file > SFTP > Browse Server and click on the server you just created ("cmuece" or whatever you named it). It should prompt you to log in and then you should see a menu with a list of files and folders you can access.

Note that because this SFTPs into the on-campus ECE machines, you will need to use a [VPN when trying to work off-campus](Working-Off-Campus).
