# Install Git

## MacOS
One easy way to install git is to install the Xcode Command Line Tools package which include Git, as well as a number of other tools.

1. Open the Terminal app
The terminal comes pre-installed on your Mac, so you have it even if you have not used it yet.
You can find it with a Spotlight Search or in the Utilities folder that is found within the Applications folder.
2. Type into the Terminal the following text: `xcode-select —install` and press return.  You'll be asked to confirm the installation, and once you do, the installation will begin.
3. Once the installation finishes successfully, you'll have Git!  Double check that you have Git by opening a new Terminal window and typing:

   `git --version`
   
   If you get a message back in the terminal like `git version 2.27.0`, that means you've successfully installed Git (even if your version number is slightly different from this example).  If you get something else back in the terminal, such as `-bash: git: command not found`, it means there has been a problem.
 4. Configure Git with your name and email by entering the following two lines in the Terminal (hitting Return after each one), subsituting your own name and email instead of `Karin Knudson` and `karin.knudson@tufts.edu`

    `git config --global user.name "Karin Knudson"`

    `git config --global user.email "karin.knudson@tufts.edu"`

    This configuration will set up Git to associate your name and email to changes that you commit to your project.

Troubleshooting: You may not be able to complete the following steps if you're running an older MacOS, such as 10.12 or earlier.  In this case, you can update your MacOS first (note that this may take some time and require a restart), and then follow the steps above.

## Linux

1. For Ubuntu or other Debian-based distributions, open the terminal and use the APT management tool to install Git:

    `apt-get install git`

     For other Linux distributions, see the analogous commands [here](https://git-scm.com/download/linux)
2. Once the installation finishes successfully, you'll have Git!  Double check that you have Git by opening a new Terminal window and typing:

   `git --version`
   
   If you get a message back in the terminal like `git version 2.27.0`, that means you've successfully installed Git (even if your version number is slightly different from this example).  If you get something else back in the terminal, such as `-bash: git: command not found`, it means there has been a problem.

 3. Configure Git with your name and email by entering the following two lines in the terminal (hitting Eeturn after each one), subsituting your own name and email instead of `Karin Knudson` and `karin.knudson@tufts.edu`

    `git config --global user.name "Karin Knudson"`

    `git config --global user.email "karin.knudson@tufts.edu"`

    This configuration will set up Git to associate your name and email to changes that you commit to your project.

## Windows

 1. Download Git for Windows [here](https://gitforwindows.org/).
 2. Start the installer and follow the instructions (the default settings should work fine).
 3. Open the Command Prompt or Git Bash (Git Bash comes along with Git for Windows).  Configure Git with your name and email by entering the following two lines (hitting Enter after each one), subsituting your own name and email instead of `Karin Knudson` and `karin.knudson@tufts.edu`

    `git config --global user.name "Karin Knudson"`

    `git config --global user.email "karin.knudson@tufts.edu"`

     This configuration will set up Git to associate your name and email to changes that you commit to your project.