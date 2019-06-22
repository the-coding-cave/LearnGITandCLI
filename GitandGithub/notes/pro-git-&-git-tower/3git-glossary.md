## Pro Git Book & Git Tower Tutorial 

Source: [Pro Git Book](https://git-scm.com/book/en/v2)
        [Git Tower - Learn Git](https://www.git-tower.com/learn/git/ebook/en/command-line/introduction)
        [Git - Learn Version Control](https://www.amazon.com/Git-step-step-Ultimate-beginners-ebook/dp/B0769JLP9C)


### Terminologies

1. _Repository (Git Repository)_: A kind of database where your VCS stores all the versions and metadata that accumulate in the course of your project. There are two kinds of repositories:  _remote_ & _local_. 

In Git, the repository is a hidden folder named ".git" in the root directory of your project. It is not to be edited. When you initialize your project as a Git repository, seeing this folder is an indication that your project is now a git repository, and changes to your code can be tracked, etc. 

2. _Remote Repository_: A "remote" repository is typically located on a remote server on the interner or in your local network. No actual working files are associated with a remote repository: it has no working directory but it exclusively consists of the ".git" repository folder. Teams use remote repositories to share and exchange data: they serve as a common base where everyone can publish the changes made in their local repo as well as recieve changes from their teammates. 

3. _Local Repository (Repo)_ : A "local" repository resides on your local computer, as a ".git" filder inside your project's root folder. This is your working copy of the entire (main) repository, you are the only person that can work with this repository. 

   * Personal Project: You can initialize a folder as a new git project or turn an existing one into a git project. 
   * Organization/Team Project: Every developer can clone a copy of the main directory (hosted on a git server/manager) to their personal computer and work on their part of the code. Their local copy (working copy) is their private workplace. Developers can make changes in their local repo (private workplace) and then commit their changes to the main (remote) repository. 

4. _Working directory_:  [The Three States](../4gitbasics.md). 
                         [The Working Tree, Staging Area (or Index), and the Local Repo](https://medium.com/@lucasmaurer/git-gud-the-working-tree-staging-area-and-local-repo-a1f0f4822018)
     It goes, working tree--> staging area (index) --> local repository. 
    
     Working Directory 
          ↓
      `git add`    
          ↓      
     Staging Area 
         ↓
     `git commit`
         ↓
     Local repository 
         ↓
     `git push origin master`
         ↓
     Remote Repository 
                      

5. _Commit_ : A commit is a wrapper for a specific set of changes. A commit message helps the developer and other developers to understand the intention behind the code changes. Every commit (set of changes) creates a new, different version of your project. Therefore, every commit also marks a specific version. A commit is a snapsht of your complete project at that certain point in time. The commit knows exactly how all of your files and directories looked and can therefore be used, e.g., to restore the project to that certain state. 

