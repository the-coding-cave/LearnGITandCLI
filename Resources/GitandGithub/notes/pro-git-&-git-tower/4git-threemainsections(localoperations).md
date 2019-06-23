
## Pro Git Book & Git Tower Tutorial 

Source: [Pro Git Book](https://git-scm.com/book/en/v2)
        [Git Tower - Learn Git](https://www.git-tower.com/learn/git/ebook/en/command-line/introduction)
        [Git - Learn Version Control](https://www.amazon.com/Git-step-step-Ultimate-beginners-ebook/dp/B0769JLP9C)


### The Three States & Main Sections
Git has three main states that your files can reside in: _committed_, _modified_, and _staged_: 

   * _Committed_ means that your data is safely stored in your local database. 
   * _Modified_ means that your have changed the file but have not commited it to your database yet. 
   * _Staged_ means that you have marked a modiefied file in its current version to go into your next commit snapshot (commit stage). 



This leads us to the main sections of a Git project: the Git directory, the working tree, and the staging area. 

   1. __The Git Directory__: git stores the metadata and object database for your project. It is what is copied when you clone a repository from another computer. It is the directory named .git. 

   2. __The Working Directory (working tree)__: the working tree is a single checkout of one version of the project. These files are pulled out of the compressed database in the Git directory and placed on disk for you to use or modify. 
  
   "The directory in which .git and all other files reside is the working directory. If you created a project locally then the directory in which you run the command `git init` is the working dir. If you cloned/downloaded the project, then the single checkout of the project is the working dir/tree." (haccks -stackoverflow)

   "The other two trees (HEAD (last commit snapshot) & Index or Staging area (proposed next commit)) store their content in an efficient but inconvenient manner, inside the .git folder. The Working Tree/Directory unpacks the content into actual files making it much easier for the developer to edit them . Think of the working dir as a sandbox, where you can try changes before commiting them to your staging area (index) and them to history." (progitbook)

   "The working copy (working dir) is the root folder of your project. It is the directory on your local computer that contains your project's files. You can always ask the version control system to populate your working copy with any version of your project. BUT you always have _one_ working copy with one specific version on your disk -not multiple in parallel.
   
   When you create a new repo (git init), you will see that a new, hidden filder was added, named ".git". All that happened is that Git created an empty local repository for your project. Emphasis on "empty", it means git did not add the current content of your copy as something like an initial version. The repository does not contain a single version of your project, yet." (git-tower)

   3. __The Staging Area (index)__: is a file generally contained in your Git directory, that stores information about what will go in your next commit. 




 __Basic Git Workflow__ 

 * (simple): 
       1. __coding in your chosen editor__ You modify files in your working tree (directory)
       2. __`git add <file>`__ You selectively stage _just_ those changes you want to be part of your next commit, which adds only those changes to the staging area. 
       3. __`git commit -m "commit message"`__ You do a commit, which takes the files as they are in the staging area and stores that snapshot permanently to your Git directory. 


 * (more steps/commands):     
      1. Initilize a git repo
         * `cd` to folder. `git init`: Initialize a new repository for an existing project/folder on your computer that is not yet under version control. 
         * `git clone [URL]`: Clone (download/copy) using a provided URL an existing git repository on a remote server (on the internet or your local network). 

      2. Once you have a local copy/local repo, you can start working on your files (working directory/working tree): modify, add, delete, rename, or move files in whatever application (fav editor, file browser, etc). 

      3. It is only when you feel you've reached a noteworthy state that you have to consider version control again. It's time to wrap your changes in a commit. But before you commit, you will want to get an overview of what you've changed so far using the command `git status`. This command will let you see what files you've changed (modified), if you've created new files or deleted some old ones. 

      4.`git add <file>` or `git add .` / `git add -A`: Next, you need to let Git know which of your local changes you want to wrap up in the next commit. Just because a file was changed doesn't mean it will be part of the next commit, git is not aware of the files you've been working on. You need to explicitly decide which changes you want to include by adding them to the staging area (index). 

      5. `git commit -m "Initial commit" `: Once the files have been added (meaning git is aware of any new changes), it is time to commit these changes (take snapshots). Include a short and meaningful message that describes what you actually did. The commit will then be recorded in your local Git repository marking a new version of your project. 

      6. `git push origin master`: You can now push this new version to a remote repository using the push command to share your changes with your team. Or pull to recieve any new changes.  
         * From time to time, you will want to have a look at what happened in the project - especially if you are working in a team. The "log" command lists all the commits that were saved in chronological order. 



     
  

    
