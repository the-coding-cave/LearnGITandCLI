## Pro Git Book & Git Tower Tutorial 

Source: [Pro Git Book](https://git-scm.com/book/en/v2)
        [Git Tower - Learn Git](https://www.git-tower.com/learn/git/ebook/en/command-line/introduction)
        [Git - Learn Version Control](https://www.amazon.com/Git-step-step-Ultimate-beginners-ebook/dp/B0769JLP9C)


### Terminologies

1. __Repository (Git Repository)__: A kind of database where your VCS stores all the versions and metadata that accumulate in the course of your project. There are two kinds of repositories:  _remote_ & _local_. 

 In Git, the repository is a hidden folder named ".git" in the root directory of your project. It is not to be edited. When you initialize your project as a Git repository, seeing this folder is an indication that your project is now a git repository, and changes to your code can be tracked, etc. 

2. __Remote Repository__: A "remote" repository is typically located on a remote server on the interner or in your local network. No actual working files are associated with a remote repository: it has no working directory but it exclusively consists of the ".git" repository folder. Teams use remote repositories to share and exchange data: they serve as a common base where everyone can publish the changes made in their local repo as well as recieve changes from their teammates. 

3. __Local Repository (Repo)__ : A "local" repository resides on your local computer, as a ".git" filder inside your project's root folder. This is your working copy of the entire (main) repository, you are the only person that can work with this repository. 

   * Personal Project: You can initialize a folder as a new git project or turn an existing one into a git project. 
   * Organization/Team Project: Every developer can clone a copy of the main directory (hosted on a git server/manager) to their personal computer and work on their part of the code. Their local copy (working copy) is their private workplace. Developers can make changes in their local repo (private workplace) and then commit their changes to the main (remote) repository. 

4. __Working directory__:  " The working directory is a single checkout of one version of the project. These files   are pulled our of the compressed database in the Git directory and placed on disk for your to use or modify."      (ProGitBook)

   [The Three States](../4gitbasics.md). 

   [The Working Tree, Staging Area (or Index), and the Local Repo](https://medium.com/@lucasmaurer/git-gud-the-working-tree-staging-area-and-local-repo-a1f0f4822018)
    
    It goes, working tree--> staging area (index) --> local repository. 
    
    Working Directory → `git add` → Staging Area →  `git commit` → Local repository →  `git push origin master` → Remote Repository 

   _The Working Tree_: is the area where you are currently working. It is where your files live. This area is known as the "untracked" area of git (untacked files). If you make changes here and do not explictly save them to git (add them), you will lose the changes. This is because git is not aware of the files or changes in the working tree until you tell it to pay attention to them. The command `git status` shows you two things: the files in your working tree (untracked files) and the files in the staging area (tracked files that are ready to be committed). 
  
   [Source](https://medium.com/@lucasmaurer/git-gud-the-working-tree-staging-area-and-local-repo-a1f0f4822018)

   _The Staging Area (or Index)_: is where git starts tracking and saving changes that occur in files. These saved changes reflect in the .git directory. When you tell git to add files (track specific files), git says okay and moves them from your working tree to the staging area. If you make any more additional changes, git will not know about them until you tell it to track those changes. You explicitly have to tell git to notice the edits in your files. 

   The command `git add <file>` will add specific file and `git add .` will add all files. 

   [Source](https://medium.com/@lucasmaurer/git-gud-the-working-tree-staging-area-and-local-repo-a1f0f4822018)

    _The Local Repository_ : is everything in your .git directory. These are all of your checkpoints or commits. It is the area that saves everything. The git command `git commit` takes all the changes in the staging area, wraps them together and puts them in your local repository. To see what is in your local repo (files within your git repo that it's tracking), type the command `git ls-tree --full-tree -r HEAD`. 
    You can also see all of the previous checkpoints by typing: `git log`. To view a specific commit : `git show   #commit#`. 

   [Source](https://medium.com/@lucasmaurer/git-gud-the-working-tree-staging-area-and-local-repo-a1f0f4822018)


5. __Commit__: A commit is a wrapper for a specific set of changes. A commit message helps the developer and other developers to understand the intention behind the code changes. Every commit (set of changes) creates a new, different version of your project. Therefore, every commit also marks a specific version. A commit is a snapsht of your complete project at that certain point in time. The commit knows exactly how all of your files and directories looked and can therefore be used, e.g., to restore the project to that certain state. 

6. __Ignoring Files__: The list of files to ignore is kept in a simple file called ".gitignore" in the root folder of your project. It is highly recommended to define this list at the start of your project -before maiing your first commit. Because once they are commit, you will have to jump through some hoops to get them out of version control. If you are on a mac, make sure your ".gitignore" file in your project root folder contains at least: .DS_Store 

You can also specify other files you want to ignore: 
   * one specific file: `path/to/file.ext` 
   * all files with a certain name: `filename.ext` 
   * all files of certain type : `*.ext`
   * files in a certain folder: `path/to/folder/*`



