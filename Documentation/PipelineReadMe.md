# Pipeline ReadMe

## Build Stage

The build stage actually consist of two jobs, the cloning job and the build job. This was done so that I could use the default: command to set the working directory to the app directory by default for the build commands, the command would likely break the clone command if it wasn't seperated.
The build commands are just taken from the flutter actions, consisting of flutter pub get to get dependencies, flutter test to run flutter app tests, and flutter build web to build the flutter webapp.

Implementing the pipeline was not much of a challenge as I just followed the Flutter action like shown in class, the only challenge I faced was with the syntax of flutter actions. I initially started every line with a - but this caused the build process to fail, I removed it from everyline except the uses and name lines.
This is more than really needed as judging by the flutter actions the syntax error likely occured from leaving the - on with. I also had some minor with the indenting of commands but that's really it. I'll update if I have any challenges with further build commands or on other stages.
