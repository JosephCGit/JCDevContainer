# Read Me

This is a basic devcontainer for Ubuntu that is designed to be used to develop a simple flutter app for an app development course. It should work on any machine that has docker desktop, though VSCode may also be required. It just uses the flutter feature for Ubuntu alongside flutter and dart extensions to install flutter. A post create command of sudo chmod is used to change file permissions so the flutter create and run -d web-server commands will work correctly.

This container currently includes the default app in flutter labeled basicapp for testing the container. Feel free to delete it and create your own app to verify flutter is installed correctly.
