

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

### Git Work Flow - Starting a new project (local)

1. `mkdir <file>` create a new project directory/folder 
2. `touch <file> `Create your files (html, css, js, node, python, etc) in your project directory. 
3. `$ git init`Initialize your project folder as a git repository. 
    * git init will create a hidden .git folder in your directory. Show hidden files will display the .git folder
4. `$ git add <file>` Add your files to the staging area for initial commit (it tracks your files)
    * `git add *.html` you can use this command to track all html files 
    * `git add .` or `git add -A` will add every file 
5. `$ git status` shows you the files in the staging area (ready to be committed)
6. ` $ git commit -m` commits your file 
    * Note that just `git commit` will open up your editor and ask you to enter a mandatory commit message for       your changes. For vim editor: press i for insert mode. scroll down to comment your message
      
      `#`
      `#`
      `#`
       my commit message
      `#`
      `#`
      `#`
    
      To get out of the insert mode, press esc. Then type in :wq 
      
      Your files will be commited 

 * `$ touch.gitignore` you can use this command to create a .gitignore file. The .gitignore file can include the      files that you do not want to push to the remote repository. 
       * in the git ignore file, typing `*.txt` ...  `*.html` ... `*.<filetype>` will ignore the files specified
 

_pushing local repository to remote repository_
8. On github.com
    * Create a new repository 
    * Since we have a local repository for the project, we do not check the option to initialize the respository      with a README. 
    * Next, we push our project respository from the command line to the new remote repository by performing the     following commands. 
         * `git remote add origin https://github.com/developer/myapp.git`
         * `git remote` should display origin
         * `git push -u origin master` should push local repository to remote repository and be able to view all your files from your local repository on github 


### Git Work Flow - Starting a new project (remote)

On github.com
* Create a new repository 
* Clone or download (to clone: copy the given link)
* Navigate via terminal or bash to your project directory 
* Type `git clone` and paste the given link : `git clone https://github.com/developer/newproject.git`
    * This will create a folder for your project with the existing files. 

### Branching & Merging in Git/Github

 Developer A has been asked to create a login feature. He performs the following commands in accordance with VCS. That is, he is not pushing his code directly to the master(main) branch. Instead he creates a new branch for the login feature, works on his code, gets the approval of his team, and then merges his code with the code on the main branch. He creates a branch called login, and works on the login feature on this branch. 


 * ` $ git status ` lets him know that he is currently on the master branch
 * ` git checkout -b login` he creates a branch called login
 * ` touch login.html` he works on the login page 
 *  Since he can also access all the files on the master branch on the login branch, he decides to make a change 
    in index.html to create a login button. 
 *  `$ git add . ` he adds the new file and changes to the index to the staging area. 
 *  `$ git commit -m "worked on login form and login button for the front page (index file)` he commits his changes
 * ` $ git checkout master`  he switches back to the master branch. Both the changes to index file and the             login.html file are not in the directory on the master branch. This is because they were made in the login        branch. The developer needs to merge the login branch and the master branch for the code that he worked on to     show up in the master. 
 *  Still on the master, he types `$ git merge login` and enters a commit message to explain why the merge is         necessary. 
 *  The merge is successful. 

        





    





