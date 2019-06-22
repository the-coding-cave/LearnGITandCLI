

# Pro Git Book & Git Tower Tutorial 

Sources: [Pro Git Book](https://git-scm.com/book/en/v2)
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

 You can think of a version control system as kind of a "database". It lets you save a snapshot of your complete project at anytime you want. When you later take a look at an older snapshot (snaphot is also reffered to as version), your VCS shows you exactly how it differed from the previous one. 

 Version Control is indeprendent of the kind of project/ technology/ framework you are working with. You can use a VCS for HTML website or a design project or an iphone app. It is simply a system that records the changes you make to your project's files. 

 __Why use Version Control?__

 [Benefits of VCS](https://www.git-tower.com/learn/git/ebook/en/command-line/basics/why-use-version-control#starts)

 __About Centralized Version Control Systems (CVCSs)__

 [Decentralized/Distributed vs Centralized VCS - Link 1](https://homes.cs.washington.edu/~mernst/advice/version-control.html#Distributed_and_centralized_version_control)
 [Distrubuted vs Centralized VCS - Link 2](https://scmquest.com/centralized-vs-distributed-version-control-systems/)
 [Distributed vs Centralized VCS -Link 3](https://www.atlassian.com/blog/software-teams/version-control-centralized-dvcs)

 _Examples of CVCS: CVS, Subversion, Perforce_

 Centralized Version control systems (CVCS) use a central server to store all files and enables team collaboration. But the main drawback of CVCS is its single point of failure, i.e., failure of the _central server_. Unfortunately, if the central server foes down for an hour, then during that hour, no one can collaborate at all. And worst case scenariom if the disk of the central server gets corrupted and proper backup has not been taken, then you lose the entire history of the project. Here is where decentralized/distribured version control system (DVCS) comes into picture. 

 __About Distributed/Decentralized Version Contol Systems (DVCSs)__

 _Examples of DVCS: Git, Mercurial, Bazaar, Darcs_

DVCS clients don't just check out the latest snapshot of files; rather, they fully mirror the repository, including its full history. Thus, if any server dies, and this systems were collaborating via that server, any of the client repos can be copied back up the the server to restore it. Every clone is really a full back up of all that data. Since Git does not rely on the central server, you can perform many operations when you are offline (commit changes, create branches, view logs, etc). You require a network connection only to publish your changes and take the latest changes. 



