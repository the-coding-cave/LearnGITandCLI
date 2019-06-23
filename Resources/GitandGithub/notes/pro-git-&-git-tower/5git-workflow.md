

## Pro Git Book & Git Tower Tutorial 

Source: [Pro Git Book](https://git-scm.com/book/en/v2)
        [Git Tower - Learn Git](https://www.git-tower.com/learn/git/ebook/en/command-line/introduction)
        [Git - Learn Version Control](https://www.amazon.com/Git-step-step-Ultimate-beginners-ebook/dp/B0769JLP9C)

### Git Workflow 

1. __Getting a Git Repository__ 
 
     * You typically obtain a Git repository in one of two ways: 
         _a._ You can take a local directory (empty or with existing files) that is currently not under version control, and turn it into a Git repository to start controlling it with Git
        
           * `git init` creates a new subdirectory named .git that contains all of your necessary repository files (a Git repository skeleton). At this point, nothing in your project is tracked yet (Git Internals will provide more info on what files are in the .git directory that is created when you perform `git init`). However if the repo was cloned then all the files are tracked and unmodified until you start making changes. 
          
           * If your local directory contains existing files that you want to start version controlling (as opposed to an empty directory), you can start tracking those files by doing an initial commit: 
            (1) ` git add <file>` or `git add . `, ` git add LICENSE` (2) `git commit -m 'initial project version`. 

         _b._ You can clone an existing Git repo from elsewhere with `git clone <url>`. 

           * This creates a directory with the name of the existing repo and initializes a .git dir inside it, pulls down all the data for that repository and checks out a working copy of the latest version. If you go into the directory that was created, you will see the project files that are ready to be worked on or used. 
        
         In either case, you end up with a Git repo on your local machine, ready for work. 

2. __Recording Changes to the Repository__

      * __In general, files can have one of two statuses in Git__: 
           
           * _Untracked_: a file that is not under version control yet is called "untracked". This means that the version control system (in our case, git) doesn't watch for (or "track") changes to this file. In most cases, these are either files that are newly created or files that are ignored and which you do not want to include in version control at all, 

           Essentially untracked files are any files in your working dir that were not in your last snapshot and are not in your staging area. When you first clone a repo, all your files will be tracked and unmodifies because Git just checked them our and ou haven't edited anything. As you edit the files, Git sees them as modified because you've changed them since your last commit. 

           * _Tracked_: all the files that are already under version control are called "tracked". They are files that that Git knows about. Git watches these files for changes and allows you to commit or discard them. They are basically the files that were in the last snapshot; they can be unmodified, modified, or staged.

           To start tracking a  new file, use the command `git add <file>` or `git add .` 

      * __To check the status of your files, run the `$ git status` command.__

          * When you first clone a repo, running the command lets you know that your branch is up to date with the origin/master, that there is nothing to commit, and your working directory is clean. The command also tells you which branch you are on. The master branch is the dedault branch.

          * If you add a new file to your project, and run the command, the status output will show you that you have untracked files. These files will be listed under the "Untracked files" heading. It basically means that Git sees a file you didn't have in the previous snapshot (commit); Git won't start including it in your commit snapshots until you explicitly tell it to do so. It does this so you don't accidentally begin included generatd binary files or other files you are not ready to include/commit. 

          * To add that new file to the staging area for git to start tracking, run the command `git add <file>`. When you run the the git status command, the file will be under the "changes to be committed" heading, which means it is staged, ready to be committed.

     * __To ignore a specific file or specific files:__


     * __To view exact changes, run the `git diff` command.__

           * This command lets you know exactly what you changed, not just which files were changed. You can use it to answer two Qs: What have you changed but not yet staged? And what have you staged that you are about to commit. While git status answers those questions very generally by listing file names, git diff shows you the exact lines added and removed -- the patch, as it were. 

              * git diff compares what is in your working directory with that is in your staging area. 

              * But to see what you've staged that will go into your next commit, run `git diff --staged` or `git diff --cached` (--staged and --cached and synonyms). They compare your staged changes to your last commit. 

     * __Commiting your changes__

          * Once you've set up your staging area, you can commit your changes. Any files that have untracked status will not be committed. 

               * The command `git commit` launches the editor of choice for you to type your commit message. It is used for longer messages. 

               * The command `git commit -m` is used for shorter commit messages. 


        * Commit records the snapshot your set up in your stagin area. Every time you perform a commit, you are recording a snapshot of your project that you can revert to or compare to later. 

     * __Skipping the Staging Area__
       
        * If you don't need to add new files and git is already tracking the files you want to commit, you can add the -a option to the git command. This makes Git automatically stage every file that is already tracked before doing the commit, letting you skip the git add part. 
       



           

          
