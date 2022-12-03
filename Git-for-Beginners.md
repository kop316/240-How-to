## Learning Git
Git is an incredibly powerful way to collaborate with others, and do version control on your code. We highly recommend learning more about it. Some guides can be found [here](https://www.digitalocean.com/community/cheatsheets/how-to-use-git-a-reference-guide), [here](https://www.digitalocean.com/community/tutorials/how-to-use-git-effectively), and [here](http://rogerdudler.github.io/git-guide/)

## Repository hosting
While a git repository can be hosted anywhere (e.g. same file system, remote client). 

CMU hosts an [ECE Gitlab instance](https://git.ece.cmu.edu/). You will not be required to create an account for this (as your ECE Account is your login), but you need to be on campus or on the [Campus VPN](Working-Off-Campus) to access it.

Other common places folks use to store git repositories are [Gitlab](https://www.gitlab.com), [Sourcehut](https://sr.ht/), and [Github](https://www.github.com). Note that these require an separate account to use them.

## Important note about repositories
If the repository will contain answers to homework or lab in the class, you must make the repository private. Otherwise, if someone finds your public repository and copies from it, you will have aided in an Academic Integrity Violation and will not enjoy the outcome.

The CMU ECE Gitlab makes repositories private by default, no others do.

## Github
You can use the website by itself to create and maintain repositories but using git in conjunction can make it really easy to maintain codebases for programming assignments. 
You can use git to create the repository but for now, use the github website to create a new repository. You can do so by navigating to the top right corner of the site and clicking on the plus, and then on _new repository_. 

![](https://i.imgur.com/moBk1Uc.png)

![](https://i.imgur.com/FjfZ9XU.png)

***

* To begin maintaining the repository within the AFS system, you want to clone it using git. To do so, in your terminal client type: `git clone [repository-link]`
  * This copies the repository as a directory in your current directory.
  * To retrieve your repository link, navigate to your repository within github and copy the _https link_. It should be in the form of _[link].git _
  * After adding some files, you can find the https link by pressing the green clone or download button. You want to copy the .git link.
  * You can then navigate to your repository directory and start adding and editing files.

![](https://i.imgur.com/jHuMHOC.png)<br/>
**NOTE: This is after you've added files to your repository. If it's freshly made, it may look like this:** <br/>
![](https://i.imgur.com/8mqzXnL.png)
***

* To add/update files to your github repository type: `git add [file-name]`
* To remove files from your github repository type: `git rm [file-name]`
  * Use the `-r` flag if you’re attempting to remove a directory and its contents.
* After adding files, you need to commit them. Type: `git commit -m “[comments]”`
  * This is where you provide details on the files you added or edited.
* To finalize your file adds, type: `git push`
  * Provide your github username and password when prompted. 
  * If done correctly, the changes should show in your repository on the github website. 


***
* To share your github repository to other people, navigate to settings -> manage access -> invite collaborator.
![](https://i.imgur.com/01TdMTP.png)
***
