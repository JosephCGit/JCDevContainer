# Source Code Version Control Tools

## Introduction
Version Control is essential in Software Development to track changes and rollback changes whenever serious bugs occur. Version control maintains integrity in software development by tracking who made what changes when. This helps to prevent programmers from claiming false credit or from shirking responsibility for breaking code.

However integrity should be held way before this point, as version control systems normally prevent changes from being made until they are pushed/committed with additional code review systems to . This means said programmer who submits broken code should have it caught before it breaks the project. 

Version Control is also extremely helpful in saving the history of a project. Since version control asks users to save any changes made to code or documents as a new version of the file, old files won't be overwritten like they are without using version control. This allows you to review older files of a project in the event of any errors and allows you to even rollback and entire project to an older version if needed.

Version Control helps with collaboration by allowing developers to freely update files without having to leave other members of the team behind. Other Team members can see when code has been changed and with version control systems like GitHub they can just pull the changed repository to be back on track. GitHub and other verso control systems can also be used to resolve conflicting changes with simple commands instead of going through an intense review process.

## Version Control System
I used GitHub with Git for version control. I did this mainly because everyone else uses it, so there is plenty of documentation about how to use GitHub with various programs including VSCode which I'm using for coding. GitHub also already has some tools to help with setting up Development pipelines such as the actions for setting up workflows.
## Repository
For now there is no branches beyond the main branch for my repository but in the future I'll try adopting a strategy of making an alternate branch for any new features such as the workflow for the pipeline. The current directory structure is one folder for the devcontainer, one folder for GitHub actions, one folder for the app and one folder for Documentation. There is an extra file for the GitHub readme.

The GitHub repository is integrated with my DevContainer using VSCode's built in GitHub source control. This helps to make using GitHub Version Control easier thanks to the UI of VSCode. I can just use the commit button for instance to push changes automatically instead of having to go through the push-pull merge request process. 

As for the Development Pipeline, GitHub integrates with that using the GitHub actions to create build, testing, and deployment scripts. There is for instance already documentation of a build script for Flutter on Linux systems.
## Common Commands
Before using any commands, you first want to use these two commands to commit any changes to your GitHub:
> git config --global user.email (Your emailname@emailservice.com)
>
>git config --global user.name (Your username)

Without these commands you will be met with an error when trying to commit any changes.

If you want to copy a GitHub repository you can use the command:
>git clone (url)

Clone will copy an entire repository, this is only recommended if your just starting to use a repository.  
If you just need to sync changes from main to your local repository use:

>git pull

Pull will copy any changes from the repository and merge them to your local branch. So if the repository has a new file, your local branch will gain that file.

If you want to change the remote branch you can use the command:

>git commit -m (message)

This will change the remote branch based on your local changes, with the -m adding a commit message to describe the change.

If you need to revert changes there are a couple of options you have:
>git revert
>
>git reset (commitname)
>
>git rebase (branchname)

Revert will revert the changes of the last commit while reset will remove history of any commits after a certain commit while rebase will apply the commits of one branch ahead of main. Rebase and reset should only be used in emergencies such as if code is extremely broken or if you accidently leave secrets in your repository.

To create and merge branches you use the following two commands:
>git branch (branchname)
>
>git merge (branchname)

Branch creates a branch with your branchname while merge will merge the named branches with main
## Collaboration
GitHub allows team members to collaborate by allowing them to change the contents of a branch on local machines independent of the branch without changing the branch itself. This helps to prevent code from breaking down in difficult to fix ways, for instance if a developer deletes a "useless" method and it breaks the functionality of a software it only breaks the functionality for that developer. That developer can then just pull the main branch and start from scratch again until they get their changes working, once they are confident in their changes they can propose changes to main which will create a pull request.

Pull Requests are very helpful in collaboration by allowing a manager to see who is making what changes in code. This can help a Manager immediately check if someone is on task or if they're off task. If they're off task this can serve as an opportunity for discussion to determine why off task edits might be made such as if they finished work early, their are unknown dependencies or worst case if a developer is doing the work of another team member because of some factor like needing help with the code or just shirking responsibility.

Pull Requests offer more help then just seeing changes, they also allow the manager to comment not only on the changes made, but the lines of code that are changed. Being able to see and comment on changes allows managers to do Code Reviews, helping to give feedback to developer on good and bad programming practices. The developers can then change the code to meet the reviewer's standards, hopefully resulting in higher quality code.

In the event that two Pull Requests conflict, GitHub allows managers to review the conflicting Pull Requests and make the decision to either go with one, the other, neither or make a change of their own by editing the conflicting file. This saves a lot of time on conflict resolution by allowing a manager to make the changes to resolve a conflict themselves. By comparison without this functionality they would have to reject both sets of changes and meet up with the conflicting developers to determine who gets to commit their change and what changes to commit if the manager feels more edits need to be made. This refers to same line conflicts, for more information about this conflict and other conflicts please read [this guide](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/addressing-merge-conflicts/resolving-a-merge-conflict-on-github). 
## Challenges and Solutions
Creating the GitHub version control wasn't as hard as setting up the DevContainer but there were some challenges. The most notable challenge I had was trying to integrate VSCode's source control with GitHub, I initially wanted to just use an already created repository and transfer my files into it but this didn't work. Instead it just created a repository named after the folder my DevContainer was in. I haven't solved this issue yet because it's not much of a problem but in the future I assume I could just rename the repository to fix this issue. The only other challenge I'm currently having is being unable to commit changes from VSCode but so far this has been fixed by just putting in my git config info. I could fix this with postcreate commands in the future to save some time.
## Conclusion
GitHub is my choice of Version Control System at this time due to it's large amount of documentation great features for setting up development pipelines and it's integration into VSCode. If this were a team project it would also be convenient for doing collaborative work with it's pull request system.

Version Control has made more mindful of the changes I make to code whilst also allowing me to fix errors if I make them. Every time I commit a change it is "permanently" recorded to GitHub and seen as the authoritative code. If I make any errors I lose my safe code and have to try to fix it again or go through the hassle of doing a reset or rebase. On the other hand though having the ability to branch code allows me to be more experimental with my code without having to worry about the above issues. Having the ability to merge changes saves me space and time that originally would have to be spent managing several different files of the same code with *slight* changes. Instead of having to delete old copies I can just merge my successful code with the original saving time and allowing me to still see the older copy.

