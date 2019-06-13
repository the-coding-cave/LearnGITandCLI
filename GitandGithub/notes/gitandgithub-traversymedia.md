

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

### Git Work Flow - Starting a new project (locally)

1. `mkdir <file>` create a new project directory/folder 
2. `touch <file> `Create your files (html, css, js, node, python, etc) in your project directory. 
3. `$ git init`Initialize your project folder as a git repository. 
    * git init will create a hidden .git folder in your directory. Show hidden files will display the .git folder
4. `$ git add <file>` Add your files to the staging area for initial commit (it tracks your files)
    * `git add *.html` you can use this command to track all html files 
    * `git add .` or `git add -A` will add every file 
5. `$ git status` shows you the files in the staging area (ready to be committed)
6. ` $ git commit -m` commits 
    * Note that just `git commit` will open up the vim editor and ask you to enter a mandatory commit message for your changes. 
qdafsbgr




