

## Notes - Git & Github Crash Course For Beginners 
##### By Brad Traversy 
[Tutorial](https://www.youtube.com/watch?v=SWYqp7iY_Tc)

### What is Git? 
Git is a __Version Control System (VCS)__ for tracking changes in computer files. 

Advantages of Git & Github: 
- [x] Distributed version control 
- [x] Coordinates work between multiple developers
- [x] Who made what changes and when 
- [x] Revert back to previous code at any time 
- [x] Local & remote repos 

_Distributed version control_: Git is a distributed version control (or decentralized version control system). This means that many developers can work on a single project without having to be on the same network. There are version control systems that developers need to be on the same network to use. That is not what Git is; Git is distributed/decentralized. 

### Concepts of Git 

* Keeps track of code history
* Takes "snapshots" of your files
* You decide when to take a snapshot by making a "commit"
* You can visit any snapshot at any time 
* You can stage files before committing

_Snapshot_: 


### Basic Commands 

* $ git init //Initialize Local Git Repository
* $ git add `<file>` // Add File(s) to the Index (staging area_. Allows you to "stage" files before commiting. 
* $ git status //Check Status of Working Tree. Allows you to see which files you have in the staging area. 
* $ git commit //Commit changes in Index. Takes everything in the index (staging area) and adds it to the local repository. 


_The next 3 commands have to do with remote repositories (github, bitbucket, and so on)_


* $ git push //pushes your local repository to a remote repository 
* $ git pull //pull latest updates from a remote repository 
* $ git clone //clone a repository into a new director at another location


Also see: [Most Basic Git Commands with Examples – a Welcome Introduction to Git](https://rubygarage.org/blog/most-basic-git-commands-with-examples)


