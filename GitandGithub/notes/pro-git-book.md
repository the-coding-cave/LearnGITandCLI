
## Pro Git 

### The Three States 
Git has three main states that your files can reside in: _committed_, _modified_, and _staged_: 

   * _Committed_ means that your data is safely stored in your local database. 
   * _Modified_ means that your have changed the file but have not commited it to your database yet. 
   * _Staged_ means that you have marked a modiefied file in its current version to go into your next commit snapshot (commit stage). 

This leads us to the main sections of a Git project: the Git directory, the working tree, and the staging area. 

  * __The Git Directory__: git stores the metadata and object database for your project. It is what is copied when you clone a repository from another computer. 
  * __The Working Directory (working tree)__: the working tree is a single checkout of one version of the project. These fiels are pulled out of the compressed database in the Git directory and placed on disk for you to use or modify. 
  * __The Staging Area (index)__: is a file generally contained in your Git directory, that stores information about what will go in your next commit. 

       * Basic Git Workflow: 
         1. __coding in your chosen editor__ You modify files in your working tree (directory)
         2. __`git add <file>`__ You selectively stage _just_ those changes you want to be part of your next commit, which adds only those changes to the staging area. 
         3. __`git commit -m "commit message"`__ You do a commit, which takes the fikles as they are in the staging area and stores that snapshot permanently to your Git directory.


