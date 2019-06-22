
## Git Tutorial

##### atlassian git tutorial 

### How Git works

 Basic overview of how Git works (_from remote to local_): 

 1. Create a "repository" (project) with a git hosting tool ( like bitbucket or github)
 2. Clone the repository to your local machine to get a local copy of the project (repository)
 3. Add a file to your local repo and "commit" (save) the changes
 4. "Push" your changes to your master branch 
 5. Make a change to your file with a git hosting tool and commit 
 6. "Pull" the changes to your local machine
 7. Create a "branch"(version), make a change, commit the change 
 8. Open a "pull request" (propose changes to the master branch)
 9. "Merge" your branch to the master branch


 ### Basic Git commands 
 [Git tutorial - basic git commands](https://www.atlassian.com/git/tutorials/svn-to-git-prepping-your-team-migration#basic-git-commands)
 [Advanced tips](https://www.atlassian.com/git/tutorials/advanced-overview)


### Setting up a repository (repo) under Git version Control 

 Objectives of this section:

 * Initializing a new Git repo
 * Cloning an existing Git repo
 * Committing a modiefied version of a file to the repo
 * Configuring a Git repo for remote collaboration
 * Common Git version control commands 

 __What is a Git Repository__ 
 A Git repository is a virtual storage of your project. It allows you to save versions of your code, which
 you can access when needed. 

 Below are workflow examples of repositories both created locally and cloned from remote repositories. You can either initialize a Git repository for a new project or clone an existing project. 

 1. __Initializing a new repository: git init__
     * Executing this command will create a new .git subdirectory(folder) in your current working directory. It will also create a new master branch. You use this command once during the initial set up of a new repo 


 2. __Versioning an existing project with a new git repository__
    * If you have an existing project that your would like to create a repo within. First cd into the root project folder then execure git init.  


 3. __Cloning an existing repository__
     * You can clone a remote repository using git clone `<repo url>`


 4. __Saving changes to the repository : git add and git commit__
     * 


 