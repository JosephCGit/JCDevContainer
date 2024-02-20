# Container Read me

Created by Joseph C

This container should work on any intel machine. If it doesn't please let me know (Addressed to my professor, but any visitor is welcome to leave a comment).

First for the container to work you need to have Flutter Desktop installed on your computer, ideally you should create an account as well but the container still worked in Docker without an account. Additionally you should have vscode installed with the devcontainer extension and git as well, this container should work on other platforms but the instructions are intended for vscode.

Install the devcontainer files (Under .devcontainer) into a folder on your explore tab (you can just create a folder by hitting open folder and then making a folder in your desired directory), the basicapp folder and gitignore are not required.

Click the blue button in the lower left corner, you should see a window with the option to reopen in container, select that option.

The container will take a while to load on first run, this is expected due to it installing flutter and changing permissions for the flutter sdk. Eventually you should see the bottom left corner change to say devcontainer ubuntu.

To create an app open a new terminal with git bash or bash selected. Then run flutter create (your appname here), if it works correctly you should see a subfolder in your current folder with the appname, then just run cd (your appname), then run flutter run -d web-server.

Two ports should open up, one will give a 404 error but another will open to the default flutter app which is just a button that increases a counter.