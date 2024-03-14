# Devcontainer Readme

## Introduction
A DevContainer is a small virtual environment created off a base image(OS) used for developing software to keep the development experience consistent for all devs. This can help avoid issues with code not working on certain hardware without having to go through the process of standardizing hardware, saving money and time. Devcontainers take up less space compared to a virtual machine allowing you to run multiple dev environments comfortably on one computer. 

For my development of the Flutter app it is more of a convenience feature that allows my professor to run the program on his machine consistently, if I were part of a development team however it would be extremely helpful in saving time setting up my computer to develop Flutter apps without having to worry that any code I use to run the app on my machine won't work on other's machines.
## Configuration
This Devcontainer is Configured off an Ubuntu image from the jammy branch, it doesn't use a DockerFile at this time but it may be updated to use one if needed. It includes the Flutter SDK feature for Ubuntu so that Flutter can be run in the DevContainer without having to run several commands to clone the Flutter SDK. It currently includes the flutter and dart extensions by default. Lastly the container is configured to run a postcreate command to change the permissions of VSCode to run Flutter.
## Integration
The Devcontainer has minimal extra integration with vscode beyond extensions which are essential to make devcontainers function in vscode such as the **Docker** extension to create dev containers and the **Dev Containers** extension which makes it easier to create said dev containers and manage them within VSCode.
## Usage
To use the container you need to do 4 key steps before being able to start
1. Install VSCode on your local machine
2. Install Docker Desktop onto your local machine
3. Install the **Docker** and **Dev Containers** extensions for VSCode
4. Use **Clone Repository** in your workspace, Download my devcontainer into a folder of your choosing, or create a folder and run:
   >git clone https://github.com/JosephCGit/JCDevContainer/

Once you have done these steps you are ready to use the Devcontainer
1. To Start the DevContainer you just need to hit the blue arrow on the lower left of vscode or type into the text box above:
   > **Reopen in Container** (If you use the blue arrow it will open a dropdown with this option)
2. On first startup it is normal if it takes a while for the container to load but once it finishes the bottom left of vscode should display devcontainer ubuntu

Depending on what you're doing you may need to follow some extra steps/tips
-If you want to edit the container you can but any edits to the code will require you to rebuild the container to take effect. VSCode should prompt you to do this but you can also hit the blue arrow on the lower left and select **Rebuild Container**.
-If you want to create and run a basic flutter application you need to follow these steps.
  1. Make sure Flutter is installed. Run the command.
     >flutter doctor
     >
     >It should print out the following assuming you don't have extra extensions
     >
     >Doctor summary (to see all details, run flutter doctor -v):
     >[✓] Flutter (Channel stable, 3.16.9, on Ubuntu 22.04.3 LTS 5.15.133.1-microsoft-standard-WSL2, locale en_US.UTF-8)
     >...(It will continue to list the status of extensions)
     
     If you don't get this output for any reason you may need to install the flutter and dart extension on your local machine. If this doesn't work you may need to try using the chown command to give flutter permissions.
  2. To create an app run the command
     >flutter create (Appnamehere)
     
     This should create a folder with the app's name in the same folder that your devcontainer file's are in.
  3. To run the app use the following string of commands
     >cd (appname)
     >flutter run -d web-server
  4. To check the app open up the ports in VSCode. Two should be active, 1 will just be a 404 error but the other should be a webpage with a button that increments a counter

## Challenges and Solutions
Initially I tried to do a clone command to install flutter, however this didn't seem to copy all files required for the Flutter SDK and VSCode didn't seem to be able to locate the Flutter SDK. You could technically work from this point by just doing steps locally to locate the Flutter SDK and install the remaining files but that defeats the point of a devcontainer so that route was scrapped. 

I then tried to use the Flutter SDK feature for Ubuntu and found it succesfully installed Flutter and could create apps, however an error would occur with permission being denied to Flutter during app creation, and trying to run the app after creation would end up causing another permission error. I tried to use the chmod on the file identified as access denied but this didn't work, then I tried to just run the blanket chmod -R command but this also didn't work, making the command a sudo command did the trick. 

These were just my issues with trying to install Flutter without investing much time into it, you could absolutely find ways to install Flutter without the feature or a way to get the Flutter SDK to work without using the chmod -R command.
## Conclusion
The Devcontainer so far has been helpful just for standardizing the environement for professor grading, if I had multiple machines it would also be helpful in allowing me to set up and do consistent development on multiple machines.

This process gave me an insight into the challenges of trying to make installation and use of software easy for an end user. Just trying to get flutter to install without additional effort on the user's end was a major challenge and that's just one program with plenty of documentation and a thankfully easy to use feature. If I went through with the clone install process it would have required far more work in terms of commands just to get it working. 

Modern game platforms like Steam are expected to present users with a well documented store page with a single install button that when hit installs an entire game and the dependencies to run it, whilst the game developers are expected to then get the game to run on the hardware with any required dependencies by the user just hitting the play buttton.
