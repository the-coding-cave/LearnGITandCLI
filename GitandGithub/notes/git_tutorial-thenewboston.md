

## Git Tutorial 
##### By thenewboston 

### Git Help 

On terminal/bash 
`git help` displays the help menu. For instance, it shows you the most commonly used git commands, along with their definition/usage.  Some are : commit, status, diff, fetch, pull, init, branch. 

To learn more about commit for example, type `git help commit` and additional information about git commit will be displayed in your default browser. 

__Commandline mini tutorial__

* `cd ` Change Directory 
* `cd .. ` Go back by once directory. Go up one. 
* `cd ../..` Go up twice. 
* `cd ~ ` Change Directory to home. Tilde symbol ~
* `cd <file>` Go to specific file 
* `pwd` Present working directory 
* `ls` List files in current directory 
* `ls -la` List hidden files in current directory 
* `clear` clears the screen (note: you can still scroll up to see previous activities)
*  _up arrow_ : shows your previous commands 

### Creating a repository 

`$ git init` means initialize or start a git repository/project
We can turn a folder on our desktop into a git project by creating a repository. Once we create a git project/repository, git starts keeping track of the changes in the project/repository. 


### Git Commit 

Commiting in git is a 2-step process. 

`$ git add . ` Means git keep track of all of the changes we made to our project/directory/repository. For example, if we created a html file, we are letting git know that we made changes to the directory and that it should add those changes (the html file). Also, the dot(.) means folder or directory. 

`$ git commit -m "message" ` Saving the entire project at that point in time (snapshot). The message lets us know exactly what we did. Git takes a "snapshot" of our code and we can always come back to see that version of the code. If we ever mess up on some part of our code, we can always see and restore previous versions. 

### Commit log 

`$ git log` allows us to view our commit history. It displays the author of the commit, the date, and the commit message. 

Also, if there are multiple developers working on a single project, we can view the commits from a specific developer by typing `git log --author="User"`. 

### Git Status 
` $ git status ` displays any changes to the directory. For ex, if we modified a file or created a new file. It shows us what git is keeping track of. 

If the `git status` displays the message "nothing to commit, working directory clean", it means that there are no files that you are working on that git isn't keeping track of ; you do not have untracked files. In other words, your local directory (working copy) matches your remote directory/repository. But if you created a file and haven't committed it yet, then both directories don't match up and you need to let git know about those files in other for git to keep track of the changes (ex: code that was added or deleted) to the files. 

How it works: 

 * working copy > staging area > repository 
   
      * When we create a file - working copy. 
      * When we add a file - stage area. These are the files that are ready to be commited.
      * When we commit - goes in the repository. Snapshot of project is taken (commit). 


### Edit Files 
`git add <filename>` adds modified files to be tracked. Git tracks what was inserted(added) and what was deleted. 
`git add . ` adds all of the modified files. 

_modified_: different than file in the repository


### View the changes between your working copy (files you are working on) & the files in your repository (main project)

` $ git status ` will show you if there are any untracked files
` $ git diff ` will show you the modifications you made to your file(s). Red (original code) & Green(modified code)
` $ git add <file>` add modified files to staging area 
` $ git commit -m "message"` commit your changes (modifications)
` $ git status `  should now show nothing to commit, working directory clean. And `git diff` should show nothing     as well, because there are no differences. 

### Comparing the Staging Area with the Repository

`git diff ` only shows differences between the working copy and the respository. So if you added the files to the staging area, git diff will not display any differences. 

So how do we compare the staging area to the repository? 

We use `git diff --staged` this compares the files in the staging area with the repository. 

### How to delete files 

 `git rm <file>` removes/deletes the file. You also need to commit it, so it takes a snapshot of the point in time where you deleted the file. 

 ### How to move and rename files 

 __rename files__ 
 When you rename, you essentially delete a file and add the exact same file with a new name. 

 `git add <newfilename>`
 `git rm <oldfilename>` 

 `git status` now displays : ` renamed  <oldfilename> -> <newfilename> `

 __move files__

 In git moving a file is renaming it. So `git mv <oldfile> <newfile>` is an easier way to rename than the steps above. 

 But you can move a file to a folder. 
 `git mv <file> <folder>`

 ### Working with an Actual Website 
 






  
















