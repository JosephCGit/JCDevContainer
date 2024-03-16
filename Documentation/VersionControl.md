# Source Code Version Control Tools

## Introduction
Version Control is essential in Software Development to track changes and rollback changes whenever serious bugs occur. Version control maintains integrity in software development by tracking who made what changes when. This helps to prevent programmers from claiming false credit or from shirking responsibility for breaking code.

However integrity should be held way before this point, as version control systems normally prevent changes from being made until they are pushed/commited with additional code review systems to . This means said programmer who submits broken code should have it caught before it breaks the project. 

Version Control is also extremely helpful in saving the history of a project. Since version control asks users to save any changes made to code or documents as a new version of the file, old files won't be overwritten like they are without using version control. This allows you to review older files of a project in the event of any errors and allows you to even rollback and entire project to an older version if needed.

Version Control helps with collaboration by allowing developers to freely update files without having to leave other members of the team behind. Other Team members can see when code has been changed and with version control systems like github they can just pull the changed repository to be back on track. Github and other verso control systems can also be used to resolve conflicting changes with simple commands instead of going through an intense review process.

## Version Control System
I used Github with Git for version control. I did this mainly because everyone else uses it, so there is plenty of documentation about how to use Github with various programs including VSCode which I'm using for coding. Github also already has some tools to help with setting up Development pipelines such as the actions for setting up workflows.
## Repository
For now there is no branches beyond the main branch for my repository but in the future I'll try adopting a strategy of making an alternate branch for any new features such as the workflow for the pipeline. The current directory structure is one folder for the devcontainer, one folder for github actiions, one folder for the app and one folder for Documentation. There is an extra file for the github readme.

The Github repository is integrated with my DevContainer using VSCode's built in Github source control. This helps to make using Github Version Control easier thanks to the UI of VSCode. I can just use the commit button for instance to push changes automatically instead of having to go through the push-pull merge request process. 

As for the Development Pipeline Github integrates with that using the Github actions to create build, testing, and deployment scripts. There is for instance already documentation of a build script for Flutter on Linux systems.
## Common Commands

## Collaboration

## Challenges and Solutions

## Conclusion
