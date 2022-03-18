# Install Git

## MacOS
One easy way to install Git is to install the Xcode Command Line Tools package which include Git, as well as a number of other tools.

1. Open the Terminal app. Terminal comes pre-installed on your Mac.
You can find it with a Spotlight Search or in the Utilities folder within the Applications folder.

2. Check if you have git already. In the terminal, type

    `git --version`
    
   a. If you get a message back in the terminal that tells you some sort of version number `git version 2.31.1`, you are all set with the installation and can skip ahead to the "configure git" step!
   
   b. If you don't get a message about the version number, you may get a message prompting you to install git, and you can follow those instructions.     
   c. If you get neither a version number nor installation instructions type into the Terminal the following text: `xcode-select -—install` and press return.  You'll be asked to confirm the installation, and once you do, the installation will begin.
   
3. Once the installation finishes successfully, you'll have Git. Double check by opening a new Terminal window and typing:

   `git --version`
   
   If you get a message back in the terminal like `git version 2.31.1`, that means you've successfully installed Git (even if your version number is slightly different from this example).  If you get something else back in the terminal, such as `-bash: git: command not found`, it means there has been a problem.
   
 4. Configure Git by entering the following three lines in the Terminal (hitting Return after each one), subsituting your own name and email instead of `Karin Knudson` and `karin.knudson@tufts.edu`. 

    `git config --global user.name "Karin Knudson"`

    `git config --global user.email "karin.knudson@tufts.edu"`

    `git config --global init.defaultBranch main`
    
The first two lines of this configuration will set up Git to associate your name and email to changes that you commit to your project, and the third one will set the default branch name to be `main`. Note: `git config --global init.defaultBranch main` will only work with Git version 2.28.0 or later. 

Troubleshooting: You may not be able to complete the preceding steps if you're running an older MacOS, such as 10.12 or earlier.  In this case, you can update your MacOS first (note that this may take some time and require a restart), and then follow the steps above. 

## Linux

1. For Ubuntu or other Debian-based distributions, open the terminal and use the APT management tool to install Git:

    `apt-get install git`

     For other Linux distributions, see the analogous commands [here](https://git-scm.com/download/linux).
2. Once the installation finishes successfully, you'll have Git!  Double check that you have Git by opening a new Terminal window and typing:

   `git --version`
   
   If you get a message back in the terminal like `git version 2.27.0`, that means you've successfully installed Git (even if your version number is slightly different from this example).  If you get something else back in the terminal, such as `-bash: git: command not found`, it means there has been a problem.

 3. Configure Git by entering the following three lines in the Terminal (hitting Return after each one), subsituting your own name and email instead of `Karin Knudson` and `karin.knudson@tufts.edu`. 

    `git config --global user.name "Karin Knudson"`

    `git config --global user.email "karin.knudson@tufts.edu"`

    `git config --global init.defaultBranch main`
    
The first two lines of this configuration will set up Git to associate your name and email to changes that you commit to your project, and the third one will set the default branch name to be `main`. Note: `git config --global init.defaultBranch main` will only work with Git version 2.28.0 or later. 


## Windows

 1. Download Git for Windows [here](https://gitforwindows.org/).
 2. Start the installer and follow the instructions (the default settings should work fine).
 3. Open the Command Prompt or Git Bash (Git Bash comes along with Git for Windows).   Configure Git by entering the following three lines in the Terminal (hitting Return after each one), subsituting your own name and email instead of `Karin Knudson` and `karin.knudson@tufts.edu`. 

    `git config --global user.name "Karin Knudson"`

    `git config --global user.email "karin.knudson@tufts.edu"`

    `git config --global init.defaultBranch main`
    
The first two lines of this configuration will set up Git to associate your name and email to changes that you commit to your project, and the third one will set the default branch name to be `main`. Note: `git config --global init.defaultBranch main` will only work with Git version 2.28.0 or later. 
