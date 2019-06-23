

# Pro Git Book & Git Tower Tutorial 

Sources: 
[Pro Git Book](https://git-scm.com/book/en/v2)
 
[Git Tower - Learn Git](https://www.git-tower.com/learn/git/ebook/en/command-line/introduction)
  
[Git - Learn Version Control](https://www.amazon.com/Git-step-step-Ultimate-beginners-ebook/dp/B0769JLP9C)

### Version Control Systems (VCS)

__What is Version Control?__

Version control is a system that records changes to a file or set of files over time so that you can recall specific versions later. If you are a graphic or web designer and want to keep every version of an image or layout, you can use a VCS to keep track of changes. VCS allows you to: 

  * revert selected files back to a previous state
  * revert the entire project bask to a previous state 
  * compare changes over time
  * maintain a history of every version
  * see who last modified something that might be causing a problem
  * see who introduced an issue and when 

 Using a VCS also generally means that if you screw things up or lose files, you can easily recover them. It also helps developers avoid overwriting each other's changes and allows them to work simultaneously. 

 You can think of a version control system as kind of a "database". Version control uses a repository (a databases of changes) and a working copy where you do your work.  VCSs lets you save a snapshot of your complete project at anytime you want. When you later take a look at an older snapshot (snaphot is also reffered to as version), your VCS shows you exactly how it differed from the previous one. 

 Your working copy (sometimes called a _checkout_) is your personal copy of all the files in the project. You make arbitrary edits to this copy, without affecting your teammates. When you are happy with your edits, you _commit_ your changes to a repository. 

 A repository is a database of all the edits to, and/or historical version (snapshots) of, your project. It is possible for the repository to contain edits that have not yet been applied to your working copy. You can update your working copy (git pull) to incorporate any new edits or versions that have been added to the repo since the last time you updated. 

 Working copy (make edits here) ------------>commit -----> Repository(database of edits/version)

 Repository (database of edits/version) -------->update-----> Working copy (make edits here)



 Version Control is indeprendent of the kind of project/ technology/ framework you are working with. You can use a VCS for HTML website or a design project or an iphone app. It is simply a system that records the changes you make to your project's files. 

 __Why use Version Control?__

 [Benefits of VCS](https://www.git-tower.com/learn/git/ebook/en/command-line/basics/why-use-version-control#starts)

 
 __Centralized vs Decentralized Version Control Systems__
 There are two general varieties of version control: centralized and distributed (decentralized). Distributed verson control is more modern, run faster, is less prone to errors, has more features, and is somewhat more complex to understand. 

 Popular version control systems are Git (distributed), Mercurial(distributed), and Subversion(centralized). 

 The main difference between centralized and distributed version is the number of repositories. In centralized version control, there is just one repository, and in distibuted version control, there are multiple repositories. 

  * CVCSs Work flow: 
   In centralized version control, each user gets his or her own working copy, but there is just one central repository. As soon as you commit, it is possibe for your co-workers to update and see your changes. But for others to see your change, 2 things must happen: (1)You commit, (2) They update. 


  * DVCSs Work flow: 
  In distributed version control, each user gets his or her own repository and working copy. After you commit, others have no access your changes until you push your changes to the central repository. When you update, you do not get others' changes unless have first pulled those changes int your repository. For others to see your changes, 4 things must happen: (1) You commit, (2) You push, (3) They pull, (4) They update. 

  The commit and update commands only move changes between the working copy and local repo, without affecting any other repo. By contrast, the push and pull commands move changes between the local repo and central repo without affecting your working copy. 

 __About Centralized Version Control Systems (CVCSs)__

 [Decentralized/Distributed vs Centralized VCS - Link 1](https://homes.cs.washington.edu/~mernst/advice/version-control.html#Distributed_and_centralized_version_control)

 [Distrubuted vs Centralized VCS - Link 2](https://scmquest.com/centralized-vs-distributed-version-control-systems/)
 
 [Distributed vs Centralized VCS -Link 3](https://www.atlassian.com/blog/software-teams/version-control-centralized-dvcs)

 _Examples of CVCS: CVS, Subversion, Perforce_

 Centralized Version control systems (CVCS) use a central server to store all files and enables team collaboration. But the main drawback of CVCS is its single point of failure, i.e., failure of the _central server_. Unfortunately, if the central server foes down for an hour, then during that hour, no one can collaborate at all. And worst case scenariom if the disk of the central server gets corrupted and proper backup has not been taken, then you lose the entire history of the project. Here is where decentralized/distribured version control system (DVCS) comes into picture. 

 __About Distributed/Decentralized Version Contol Systems (DVCSs)__

 _Examples of DVCS: Git, Mercurial, Bazaar, Darcs_

DVCS clients don't just check out the latest snapshot of files; rather, they fully mirror the repository, including its full history. Thus, if any server dies, and this systems were collaborating via that server, any of the client repos can be copied back up the the server to restore it. Every clone is really a full back up of all that data. Since Git does not rely on the central server, you can perform many operations when you are offline (commit changes, create branches, view logs, etc). You require a network connection only to publish your changes and take the latest changes. 

__Version Control best practices (centralized and decentralized)__

 1. _Use a descriptive commit message_ : It only takes a moment to write a good commit message. This is useful when someone is examinining the change, because it indicates the purpose of the change. It is also useful when someone is looking for changes related to a given concept, because they can search through the commit messages. Begin your message with a short summary of your changes. Separate it from the body by including a blank line. The body of your message should provide detailed answers to the following Qs: What was the motivation for the change? How does it differ from the previous version?

 If your commit message is very long, omit the "-m" parameter and Git will open an editor for you to include your message.

 2. _Make each commit a logical unit_: Each commit should have a single purpose and should completely implement that purpose. This makes it easier to locate the changes related to some particular feature or bug fix, to see them all in one place, to undo them, to determine the changes that are responsible for buggy behaviour, etc. The utility of the version control history is compromised if one commit contains code that serves multiple purposes, or if code for a particular purpose is spread across multiple different commits. 

 So when crafting a commit, include only changes that belong together. For instance, imagine wrapping both some work for your new login functionality and a fix for bug #122 in the same commit: 

   * Understanding what all those changes really mean and do gets hard for your teammates (and, after sometime, also for yourself). Someone who is trying to understand the progess of the new login functionality will have to untangle it from the bugfix code first. Try to only wrap related changes. Fixing two different bugs should produce (at the very least) two separate commits. 
   
   * Undoing one of the topics gets impossible. Maybe your login functionality introduced a new bug. You can't undo just this one without undoing your work for fix #122, also! 

  The staging area can be used to make meaningful commits, as it allows you to determine which of your local changes shall be committed. 

 3. _Commit only completed work_: Never commit something that is half done. 

 4. _Commit tested work_: Do not commit code that you "think" is working. Test it well before you commit it to the repo. 

 5. _Commit often_: This will automatically help you keep your commits small and only include related changes. 

  [Read more (1)](https://homes.cs.washington.edu/~mernst/advice/version-control.html#Introduction_to_version_control)

  [Read more (2)](https://www.git-tower.com/learn/git/ebook/en/command-line/basics/working-on-your-project#start)

__Typical workflow__
The typical workflow when using Git (or Mercurial) is:

* git pull (or hg fetch)
* As many times as desired (but usually very few times):
   * Make local edits
   * Examine the local edits: git status and git diff (or hg status and hg diff
   * git commit (or hg commit)
* git pull or git pull -r (or hg commit)
* git push (or hg push)



 _Note that an invocation of git pull or hg fetch may force you to resolve a conflict._
 _In Mercurial, use hg fetch, not hg pull_
 _(This tip is specific to Mercurial. In Git, just use git pull. Git's pull acts similarly to Mercurial's fetch.)_






