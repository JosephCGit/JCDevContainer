# Devcontainer ReadME

## Introduction
A DevContainer is a small virtual environment used for developing software to keep the development experience consistent for all devs. This can help avoid issues with code not working on certain hardware, or as it's known "It works on my machine". Devcontainers take up less space compared to a hardware environment or virtual machine.
## Configuration
This Devcontainer is Configured off an Ubuntu image from the jammy branch, it doesn't use a DockerFile at this time but it may be updated to use one if needed. It includes the Flutter SDK feature for Ubuntu so that Flutter can be run in the DevContainer without having to run several commands to clone the Flutter SDK. It currently includes the flutter and dart extensions by default. Lastly the container is configured to run a postcreate command to change the permissions of VSCode to run Flutter.
## Integration

## Usage

## Challenges and Solutions
Initially I tried to do a clone command to install flutter, however this didn't seem to copy all files required for the Flutter SDK and VSCode didn't seem to be able to locate the Flutter SDK. You could technically work from this point by just doing steps locally to locate the Flutter SDK and install the remaining files but that defeats the point of a devcontainer so that route was scrapped. I then tried to use the Flutter SDK feature for Ubuntu and found it succesfully installed Flutter and could create apps, however an error would occur with permission being denied to Flutter during app creation, and trying to run the app after creation would end up causing another permission error. I tried to use the chmod on the file identified as access denied but this didn't work, then I tried to just run the blanket chmod -R command but this also didn't work, making the command a sudo command did the trick. These were just my issues with trying to install Flutter without investing much time into it, you could absolutely find ways to install Flutter without the feature or a way to get the Flutter SDK to work without using the chmod -R command.
## Conclusion
