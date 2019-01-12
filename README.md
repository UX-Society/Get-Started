# Before Starting

Ask an Admin for the https://github.com/UXSoc Github group to invite you, which can be done through People > Invite Member. Then navigate to the same page and accept the invite. 

**If you are using Windows make sure it is on the latest branch and version before starting**
____

# Terminal 

The terminal is a powerful way to use a computer and learning how to use it properly important for serious work. Using the terminal is easy for macOS/OS X and other Linux based computers and replacing bash with fish will make it even easier. Windows is not recommended for dev work, but skip to [the Windows section](https://github.com/UXSoc/Get-Started#windows) for help with setup. To use the terminal a command has to be given which follows this general format.
```
    username@hostname:location$ "command name" "command sub-name" -arguments "info"
```
For example:
```
    sudo apt-get install -y fish
```
To break this command down, it starts with 'sudo' which indicated that the command is being run with max user authorization, use it very carefully. 'apt-get' is the main command and it tell the computer that I want to manage my packages (package is a name for a software bundle, which has been replace by App). 'install' tells the computer that I want to install a package, a feature of apt-get. '-y' is an argument denoted by the dash and slightly changes what the computer does, in this case to automatically skips the installation confirmation dialogue. 'fish' is the info of what is being done, in this case the package installed.

Here are some useful commands:

- cd: 'change directory' - it moves you around the filesystem. Ex:  `cd WebstormProjects/yourProject/`
- ls: 'list directory contents' - tells you all the files in the current dir. Ex: `ls -a`
- man: 'manual' - tells you how to use a command. Ex: `man man` (tells you how to use itself)
- git: this command is used to manage software versions and will be explained later

### Tips
- Use the up arrow (↑) to scroll through command history
- The upper-left generally will have the current working directory so make sure to run commands in the right place
- Ctrl-L will clear the console
- Ctrl-C stops the currently running command

### Terminal examples

`gitadd*` :negative_squared_cross_mark:, make sure to put a space between each part of the command

`Git Add *` :negative_squared_cross_mark:, don't capitalize commands

`git add *` :heavy_check_mark:

# Github
Github is a powerful version control platform used by us and also numerous professional. This Tutorial will go through set-up and basic usage of git and Github.

First go to https://github.com/UXSoc and create an account using your *Chapman email*.

After that, go to https://education.github.com/pack to claim free stuff. (Note: only email addresses ending in @chapman.edu will automatically get automatically approved, NOT @mail.chapman.edu)

## Set-up SSH

Next add a key to GitHub so you can use SSH:

1)  Open a terminal and paste `ssh-keygen -t rsa -b 4096 -C "your_email@example.com"` **(press enter to skip all prompts)**
2)  As long as you didn't set a different location go to the .ssh diretory ` cd ~/.ssh/` 
3) Print out the key with `cat id_rsa.pub`
4) Copy it from terminal (Tip: Ctrl-V will likely not work, instead Highlight -> Right-Click -> Copy)
5) Go to Github and go to https://github.com/settings/keys 
6) Click on `New SSH Key` paste and confirm
7) Run `ssh -T git@github.com` and answer 'yes' so GitHub is trusted


After that is working, run the following to set-up git locally:
```
git config --global user.name "Your Name"
git config --global user.email your_email@chapman.edu
```

## Clone Test

With your account set-up, now a project has to be cloned in order to edit it. To start clone this project which can be found in the UX Github page as **Get Started**

1. Click the *'fork'* button in the upper right to make a personal copy of this project
1. From your on github click on **Clone or Download**
1. Click on **Use SSH** and copy the link there
1. Run the command `git clone git@github.com:UXSoc/Get-Started.git` to create a directory will all of the project's content
1. Open the cloneme.txt file and add your name, and save
1. Run `git add cloneme.txt` to add it to git tracking
1. Run `git commit -m "Your message here"` to commit your changes to the master branch then `git push` to update to your changes
1. Check the online version to make sure your changes have been recorded

### Tips 

- If there is an error try running `git add [file location]` to resolve it
- Webstorm can handle git/Github instead and includes UI elements which may make your life easier

# Webstorm
Webstorm is the Webdev IDE that we use because it is free to students and fully-featured.

Install by going to https://account.jetbrains.com/login and signing up with you *Chapman email*, then go to https://www.jetbrains.com/student/ and using apply. Then go to https://www.jetbrains.com/webstorm/ download and sign in to use for free.

Next install and login into Webstorm. Make sure to select the markdown plugin when installing.

Inside Webstorm use **Check out from Version Control** and sign into Github to automatically clone and manage a project. 

![screenshot of file display in Webstorm](/Pictures/filemanager.png) 
The left column shows the open project's file-system

![screentshot of editable area](/Pictures/edit.png)
The right area is where files are edited and closed

![screenshot of pop-up](/Pictures/events.png) 

The bottom will sometime have a pop-up that gives errors and other info about the project

## Webstorm VCS

The **VCS** menu also can manage the project's version, make sure add the account in Settings > Version Control > Github > '+' button on the right.

Use the **Commit** sub-menu option to see all the files being commited, individual changes, and add a message there too. Commits can also be pushed from the arrow on the commit button at the same time.

Don't forget to use **VCS > Update Project** to get the most recent files.
If the clone is from a fork and not a true master do `git remote set-url origin git@github.com:UXSoc/[repo name].git` before updating, then change it back to your fork.


## Pull Request
Instead of allowing members to directly contribute, the project manager looks over pull requests for changes.
- Fork the repository, and go to your personal version
- Clone that repo locally
- Commit and push to you repo
- On te github page, go to the *Pull requests* tab and open a new request (note: future commits will be automatically added to the request)
- Wait or notify the PM of the request, then see if they were rejected or accepted

# Windows
This section is only for Windows users to set-up a Unix like environment to have an easier time developing and using our products.

- Open PowerShell as Admin, Start Menu > Search for "powershell" > Right-click > "Run as Administrator" > Click "yes"
- Run the command `Enable-WindowsOptionalFeature -Online -FeatureName Microsoft-Windows-Subsystem-Linux`, restart when prompted
- Go to [Microsoft Store](https://www.microsoft.com/en-us/p/ubuntu/9nblggh4msv6) and install Ubuntu subsystem

### Setup

After installing you can access you're files with the command `cd /mnt/c` and then navigate to them by going to the *Users* folder and then your Windows user folder.

Don't want to navigate that every time? No problem just follow these steps
- On launch type `nano .bashrc`
- At the bottom of the file add the command to change into your directory it should look like:
```
cd /mnt/c/Users/[Your Username]
```
- Ctrl-V doesn't work, the only way to copy or paste is to Right-click which saves or fills data.
- You can optionally add /WebStormProjects after your username too, to always open to up there
- It is best to test out the cd command before adding it to the *.bashrc* to see if it works
- Add the command `fish` after that line to also automatically open fish if it is installed, see [fish here](https://github.com/UXSoc/Get-Started#fish)

### Add Git to Windows
If Ubuntu for Windows can't install or you want to use Git version contol inside Webstorm, try [Git for Windows](https://github.com/git-for-windows/git/releases/download/v2.19.1.windows.1/Git-2.19.1-64-bit.exe). Note: download starts immediatly.

### After installing Webstorm
If you are also using Webstorm on Windows make sure to **uncheck** File > Settings > Appearance & Behavoir > System Settings > Synchronization > 'Use "safe write"'

![Screenshot of turning off safe write](Pictures/saynotosafewrite.png)

Not doing this results in an error in Webstorm when running a watcher and trying to edit files.

# Learning Webdev
Individual projects will use different libraries and support tools, but they all share the central pillars of a webpage.

- HTML is the backbone and structural component of the site. It gives layout and links documents together
- CSS is the styling of a site and makes it look good
- Javascript is the functional part of a site and provides features that HTML  and CSS cannot

### Tips
- Right-click > **Inspect** is extremely valuable for webdev. From the dev tools HTML can be viewed, and CSS can be de-bugged. For example the selected element's padding, margins etc can be seen with the box-viewer. The Javascript console is also available.
![](/Pictures/viewCss.png)
- Don't forget to Google 'css thing' if you're unsure of what to do. There are many resources available online to learn 
- If the website is not updating to changes, **Inspect > Network > check Disable Cache** or also right click the reload button with Inspect tools open
- https://developer.mozilla.org/en-US/ is a great resource for almost anything webdev
- An easy way to install node for Ubuntu: [or any package manager](https://nodejs.org/en/download/package-manager/#debian-and-ubuntu-based-linux-distributions)

### Fish
[Fish Shell](https://fishshell.com/) is recommended to make console usage easy.

Test it out with the command `fish` in terminal or run `sudo chsh -s /usr/bin/fish` and restart to set it as the default shell. 

See [this documentation](https://github.com/fish-shell/fish-shell#packages-for-linux) for how to install on Ubuntu, Debian, or Ubuntu for Windows

### Atom
[Atom](https://atom.io/) is recommended for those who can't aquire Webstorm or when Webstorm is to resource heavy to run on a computer.

It also supports hot-reload from disk and doesn't require the window to be refocused. 
