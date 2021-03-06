# Windows: Installing using WSL


To develop web apps you need some tools on your laptop. This guide helps you with installing al these tools.

We will be using the [_Windows Subsystem for Linux 2_](https://aka.ms/wsl2).

Note: These instruction are written for Windows 10. If you're using Windows 8 or older please follow [these](/install/windows8) instructions.

## Step 1: Install the Windows Subsystem for Linux

Start with opening PowerShell as Administrator.
Right-click the Start button and click "Windows PowerShell (Admin)"

Run:

    dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart

This will install the Windows Subsystem for Linux.


## Step 2: Update to WSL 2

The get better performance we want the upgrade to WSL 2.

Run:

    dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart

This will enable the "Virtual Machine Platform", this is needed for WSL2.

Then enable WSL2:

    wsl --set-default-version 2

This might result in `WSL 2 requires an update to its kernel component. For information please visit https://aka.ms/wsl2kernel`.
Go to [https://aka.ms/wsl2kernel](https://aka.ms/wsl2kernel) and install the update and retry the command above.


## Step 3: Install Ubuntu for WSL

1. Head to [Microsoft Store Ubuntu](https://www.microsoft.com/store/apps/9n6svws3rx71)-page. And install Ubuntu 20.04.
2. Launch Ubuntu 20.04, this will take a few minutes.
3. Enter a username and password for Ubuntu.
    - Linux will not show any characters while entering a password, this is normal.
4. Start with updating Ubuntu run:

        sudo apt update && sudo apt upgrade -y


## Step 4: Install Python, Pip, Sass and Django

Run:

    sudo apt install python3-pip ruby-sass -y

This will install Pip (Python's package manager) and Sass.

Run:

    pip3 install django

This will install the Python package _Django_.


## Step 5: Install a text editor

Those of you who have taken CS50 are used to working from within the IDE. In this course, we remove those training wheels. This means you have to download and install a text editor on your own computer.

Visual Studio Code is a text-editor made by Microsoft, it fully integrates with the WSL. It can be downloaded [here](https://code.visualstudio.com/).

You are free to use an other editor like [Atom](https://atom.io/) or [Sublime Text](https://www.sublimetext.com/), but we recommend [Visual Studio Code](https://code.visualstudio.com/).


## Using the WSL in VSCode

You can now start using Ubuntu via WSL. When you open VSCode, make sure it is using Ubuntu.

The WSL is not enabled right now, click the green button to enable it.

![](wsl/wsl_disabled.png)

Select "Remote_WSL: New Window" to enable the WSL.

![](wsl/wsl_enable.png)


If the WSL is enabled, it should look like this.

![](wsl/wsl_enabled.png)


## Tips and tricks

- Open the current folder in VSCode from within WSL: Ubuntu: `code .`.
- Open a terminal window in VSCode with `ctrl-j`.


# Troubleshooting
Ran into trouble? Contact the staff! It's important to get started quickly. You only have to do the above once, so get help now and you'll be set for the remainder of the course!
