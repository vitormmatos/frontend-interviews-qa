# Git

<link href="./ASSETS/STYLES.css" rel="stylesheet"></link>
<img src="./ASSETS/GIT.svg" alt="Git Logo" class="logo"></img>

- [What is Git?](#what-is-git)
- [What is a git repository?](#what-is-a-git-repository)
- [What does git clone do?](#what-does-git-clone-do)
- [What is Github?](#what-is-github)
- [What are the benefits of using Version Control System?](#what-are-the-benefits-of-using-version-control-system)
- [What is a conflict?](#what-is-a-conflict)
- [What are the usages of git stash](#what-are-the-usages-of-git-stash)

## What is **Git**?

Git is a free and open source distributed version control system.

Usually used for coordinating work among programmers collaboratively developing source code during software development.  
Its goals include speed, data integrity, and support for distributed, non-linear workflows

**[⬆ Back to Top](#git)**

## What is a git **repository**?

A repository is a file structure where git stores all the project-based files.  
Git can either stores the files on the local or the remote repository.

**[⬆ Back to Top](#git)**

## What does **git clone** do?

The command creates a copy (or clone) of an existing git repository.  
Generally, it is used to get a copy of the remote repository to the local repository.

**[⬆ Back to Top](#git)**

## What is **Github**?

GitHub is a Git repository hosting service, plus it adds many of its own features.  
GitHub provides a Web-based graphical interface.   
It also provides access control and several collaboration features, basic task management tools for every project.

**[⬆ Back to Top](#git)**

## What are the benefits of using **Version Control System**?

With the Version Control System(VCS), all the team members are allowed to work freely on any file at any time.  
VCS gives you the flexibility to merge all the changes into a common version.

All the previous versions and variants are neatly packed up inside the VCS.  
You can request any version at any time as per your requirement and you’ll have a snapshot of the complete project right at hand.

Whenever you save a new version of your project, your VCS requires you to provide a short description of the changes that you have made.  
Additionally, you can see what changes are made in the file’s content. This helps you to know what changes have been made in the project and by whom.

A distributed VCS like Git allows all the team members to have a complete history of the project so if there is a breakdown in the central server you can use any of your teammate’s local Git repository.

**[⬆ Back to Top](#git)**

## What is a **conflict**?

Git usually handles feature merges automatically but sometimes while working in a team environment, there might be cases of conflicts such as:

1. When two separate branches have changes to the same line in a file
2. A file is deleted in one branch but has been modified in the other.
 
These conflicts have to be solved manually after discussion with the team as git will not be able to predict what and whose changes have to be given precedence.

**[⬆ Back to Top](#git)**

## What are the usages of git stash?

Git stash can be used in cases where we need to switch in between branches and at the same time not wanting to lose edits in the current branch.

Running the git stash command basically pushes the current working directory state and index to the stack for future use and thereby providing a clean working directory for other tasks.

**[⬆ Back to Top](#git)**
