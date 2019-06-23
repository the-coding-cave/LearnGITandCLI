

## Pro Git Book & Git Tower Tutorial 

Source: [Pro Git Book](https://git-scm.com/book/en/v2)
        [Git Tower - Learn Git](https://www.git-tower.com/learn/git/ebook/en/command-line/introduction)
        [Git - Learn Version Control](https://www.amazon.com/Git-step-step-Ultimate-beginners-ebook/dp/B0769JLP9C)

### Git Workflow 

1. __Getting a Git Repository__ 
 
     * You typically obtain a Git repository in one of two ways: 
    
       * One. You can take a local directory (empty or with existing files) that is currently not under version control, and turn it into a Git repository to start controlling it with Git.   `git init` creates a new subdirectory named .git that contains all of your necessary repository files (a Git repository skeleton). At this point, nothing in your project is tracked yet (Git Internals will provide more info on what files are in the .git directory that is created when you perform `git init`). However if the repo was cloned then all the files are tracked and unmodified until you start making changes.  If your local directory contains existing files that you want to start version controlling (as opposed to an empty directory), you can start tracking those files by doing an initial commit:   (1) ` git add <file>` or `git add . `, ` git add LICENSE` (2) `git commit -m 'initial project version`. 

       * Two. You can clone an existing Git repo from elsewhere with `git clone <url>`.  This creates a directory with the name of the existing repo and initializes a .git dir inside it, pulls down all the data for that repository and checks out a working copy of the latest version. If you go into the directory that was created, you will see the project files that are ready to be worked on or used. 
        
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


     * __To view exact changes, run the git diff command.__:  This command lets you know exactly what you changed, not just which files were changed. You can use it to answer two Qs: What have you changed but not yet staged? And what have you staged that you are about to commit. While git status answers those questions very generally by listing file names, git diff shows you the exact lines added and removed -- the patch, as it were. 

         * git diff compares what is in your working directory with that is in your staging area. 

         * But to see what you've staged that will go into your next commit, run `git diff --staged` or `git diff --cached` (--staged and --cached and synonyms). They compare your staged changes to your last commit. 

     * __Commiting your changes__

          * Once you've set up your staging area, you can commit your changes. Any files that have untracked status will not be committed. 

               * The command `git commit` launches the editor of choice for you to type your commit message. It is used for longer messages. 

               * The command `git commit -m` is used for shorter commit messages. 


        * Commit records the snapshot your set up in your stagin area. Every time you perform a commit, you are recording a snapshot of your project that you can revert to or compare to later. 

     * __Skipping the Staging Area__ 
     
       * If you don't need to add new files and git is already tracking the files you want to commit, you can add the -a option to the git command. This makes Git automatically stage every file that is already tracked before doing the commit, letting you skip the git add part. 
       The command for this is : `git commit -a -m "commit message"`. 
       The ` -a` flag includes all changed files so you don't need to run git add before you commit. While this is convenient, be careful becauses sometimes this flag will cause you to include unwanted changes. 

     * __Removing Files__

       * To remove a file from Git, you have to remove it from your tracked files (the staging area), then commit. The `git rm` command does that, and also removes the file from your working directory so you don't see it as an untracked file the next time. If you simply remove the files from your working directory, it still shows up under changes not staged for commit. To remove the file run ` $ git rm <file>`.  The next time you commit, the file will be gone and no longer tracked. 

       If you modified the file or had already added it to the staging area, you must force the removal with the `-f` option. 

       Also if you want to keep the file in your working tree (dir) but remove it from the staging area. Meaning, you want to keep the file on your hard drive but not have Git track it anymore. Particularly useful if you forgot to add something to your .gitignore file and accidentally staged it, and so on. The command to remove it from the staging area is to use the --cached option. So, `$ git rm --cached <file>`. 

       
     * __Moving files in Git is the same as renaming files__

     To rename a file in Git , you can run the command `$ git mv <file 1> <file 2>`

      
 3. __Viewing the Commit History__

     After you have created several commits, or if you have cloned a repo with an existing commit history, you can view them with the git log command : `$ git log `

     Git log lists the commits made in that repo in reverse chronological order; that is, the most recent commits show up first. 

     You can also add the `-p` or `--patch` option, whih shows the difference (the patch output) introduced in each commit. You can also limit the number of log entries displayed, such as using `-2` to show only the last two entries. 

     Using both options, ex: ` $ git log -p -2`

     There are many more options provided in the [book](https://git-scm.com/book/en/v2/Git-Basics-Viewing-the-Commit-History)


 4. __Undoing things__

     Below are a few basic tools for undoing changes that you've made. Be careful, because you can't always undo some of these undos. You can lose some work if you do it wrong. 

       * __Redoing commits__ : One of the common undos take place when you commit too early and possibly forget to add some files, or you mess up your ommit message. To redo that commit: (1) make the additional changes you forgot, (2) stage them and commit again using the --amend option. Which is : `$ git commit --amend`.   If you've made no changes since your last commit (for instance, you run this command immediately after your previous commit), then your snapshot will look exactly, the same and all you will change is your commit message.  The same commit-message editor will fire up with the message of your previous commit, you can then edit the message (it will overwrite your previous commit)

        Ex of the command sequence: 

         ` $ git commit -m "initial commit"` 
         ` $ git add <forgotten file>` 
         ` $ git commit -- ammend` 

       What you are doing when you ammend your commit, the second commit replaces the result of the first.  You are replacing it entirely with a new, improved commit that pushes the old commit out of the way and puts the new commit in its place. Effectively, it's as if the previous commit never happened, and it won't show up in your repository history. 

    
     * __Unstaging a Staged File__: Let's say you've changed two files and want to commit them as two separate changes, but you accidentally type ` $ git add *` and stage them both. 
     First, run the `$ git status` command, the output tells you that you can use `$ git reset HEAD <file>` to
     unstage. Note that git reset can be a dangerous command, especially if you provide the --hard flag. 

     * __Unmodifying a Modified File__: If you don't to keep the changes your made to a file, and you want to unmodify it (revert it back to wha it looked like when you last commited or initally cloned, etc), you can run the git status command as it tells you explicitly how to discard the changes you've made. 
     Use `git checkout --<file>` to discard the changes in working directory. This is also a dangerous command, any local changes you made to that file are gone. Git just replaced that file with the most recently-commited version. 

 5. __Working with Remotes__

    Remote repositories are versions of your project that are hosted on the Internet or network somewhere. To be able to collaborate on any Git project, you need to know how to manage your remote repos. Managing repositories includes knowing how to add remore repositories, remove remotes that are no loger valid, manage various remote branches and define them as being tracked or not, and more.

       * __Showing your Remotes__: To seee which remote servers you've configured, run the `git remote` command. It lists the shortnames of each remote handle you've specified. If you've cloned your repo,you should at least see origin - that is the default name Git gives to the server you cloned from. The option `-v` shows you the URLs that Git has stored for the shortname to be used when reading and writing to that remote. 
       If you have more than one remote, the command lists them all. For example, a repo with multiple remotes for working with several collaborators will list all of the remote repos. This means we can pull contrinutions from any of the users(collaborators) pretty easily. 

       * __Adding Remote Repos__: The git clone command implicitly adds the origin remote. To explicitly add a new remote Git repository as a shortname you can reference easily, run `git remote add <shortname> <url>`. 
       Ex: `git remote add pb https://github.com/paulboone/ticgit`. Now you can use the string "pb" on the command line instead of the whole URL. For example, if you want to fetch all of the information that Paul has but that you don't yet have in your repo, you can run `git fetch pb`.  Paul's master branch is now accessible locally as pb/master - you can merge it into one of your branches, or you can check out a local branch at that point if you want to inspect it. 

       * __Fetching and Pulling from Your Remotes__: You can run `git fetch <remote>` to get data from remote projects. The command goes out to that remote project and pulls down all the data from that remote project that you don't have yet. 

       `git fetch origin` fetches any new work that has been pushed to that server since you cloned (or last fetched from) it. 

       Note that git fetch only downloads the data to your local repo, it doesn't not automatically merge it with any of your work or modify what you are currently working on. You have to merge it manually into your work when you are ready. 

       If your current branch is set up to track a remote branch, you can use the git pull command to automaticall fetch and then merge that remote branch into your current branch. The git clone command automatically sets up your local master branch to track the remoe master branch. Running `git pull` generally fetches data from the server you originally cloned from and automatically tries to merge it into the code you are currently working on. 

      * __Pushing to your Remotes__: When you are ready to share your work, you can push it upstream via the command `git push <remote> <branch>`. For instance to push to the origin server, run the command `git push origin master`. Note that this command works only if you cloned from a server to which you have write access, and if nobody has pushed in the meantime. If you and someone else push upstream at the tsame time, your push will rightly be rejected. You will have to fetch their work gits and incorporate it into yours before you will be allowed to push. 


      * __Inspecting a Remote__: To see more information about a particular remote, run the command: `git remote show <remote>`. Example: `$ git remote show origin` will display information about the origin. 

      * __Renaming and Removing Remotes__: To change a remote's shortcut name: run the command `git remote rename <prev name> <new name>`. Example: `git remote rename pb paul`.  
      To remove a remote (perhaps you've moved the server, or a contributor is no longer contributing, etc), you can run `git remote remove <remotename>`. Ex: `git remote remove paul`. 

 6. __Tagging__

 7. __Git Aliases__

 










       



           

          
