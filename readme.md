# GitHub Setup for IT Programs
### NSCC Truro Campus
**Sep 2026** 

The following is a checklist of installations / configurations to setup your machine (whether it be in the lab or your home machine) to be ready for using GitHub for the school year.

1) install git on your computer
    - download git from https://git-scm.com
    - follow the installation instructions, and leave all settings as default
    - open a terminal window (Command Prompt, PowerShell, or Terminal) to your user account on your computer (e.g. C:\Users\username)
        - on a lab machine on campus this folder will be named after your student id number
    - finish configuration of git by running the following commands in your terminal window:
        ```
        git config --global user.name "Your Name"
        git config --global user.email "your email address"
        ```
        - do not use your NSCC email address, use a personal email address (gmail, etc)
2) create a github account
    - go to https://github.com and create an account
    - be sure to use the same personal email address used in previous step
    - be sure to remember your username / password
3) create an SSH key to easily authenticate with github for the school year
    - run the following command in the already opened terminal window: 
        ```
        ssh-keygen
        ```
        - click enter on all options until the cursor appears again
    - change directory to the `/.ssh` folder by running the following command:
        ```
        cd .ssh
        ```
        - two keys have been created in this folder: a private key (id_ed25519) and a public key (id_ed25519.pub)
    - view the contents of the public key file by running the following command:
        ```
        type id_ed25519.pub
        ```
        - if you are running MacOS / Linux: use the command `cat id_ed25519.pub`
        - the contents of the file is displayed in the terminal window
        - it will be one single line; select it with the mouse and copy it to your clipboard (press `Ctrl+C`)
    - add the public key to your github account
        - go to your github account in a web browser (login if necessary)
        - click on your profile picture in the top-right corner, and select *Settings*
        - in the left sidebar, select *SSH and GPG keys*
        - click the green *New SSH key* button
        - in the *Title* field, enter a name for the key (e.g. LAB308 or Laptop)
        - in the *Key* field, paste the contents of your clipboard (right-click and select paste, or press `Ctrl+V`)
        - click the green *Add SSH key* button
    - test the connection to github by running the following command in your terminal window:
        ```
        ssh -T git@github.com
        ```
        - if this is your first time connecting to github, you will be asked if you want to continue connecting; type `yes` and press enter
        - you should see a message that says "Hi [your username]! You've successfully authenticated, but GitHub does not provide shell access."

:exclamation: note that an SSH key must be created on your machine in all labs on campus as well as your home machine / laptop. Repeat step 3 on all machines