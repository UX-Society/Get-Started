# Terminal 

The terminal is a powerful way to use a computer and learning how to use it properly important for serious work. Using the terminal is easy for macOs and other Linux based computers and replacing bash with fish will make it even easier. Windows is not recommended for dev work, but Cygwin or Bash for Ubuntu on Windows. To use the terminal a command has to be given which follows this general format.
```
    "command name" "command sub-name" -arguments "info"
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

# Github
Github is a powerful version control platform used by us and also numerous professional. This Tutorial will go through set-up and basic usage of git and Github.

First go to https://github.com/UXSoc and create an account using your *Chapman email*.

After that, go to https://education.github.com/pack to claim free stuff. (Note: only email addresses ending in @chapman.edu will automatically get approved)

Next, connect your Github account to your computer using ssh keys ________________.

Will your account set-up a project has to be cloned in order to edit it. To start clone this project which can be found in the UX Github page as **Get Started**

1) Navigate to the page and click on **Clone or Download**
2) Click on **Use SSH** and copy the link there
3) Run the command `git clone git@github.com:UXSoc/Get-Started.git` to create a directory will all of the project's content
4) Open the cloneme.txt file and add your name
5) Run `git push` to update to your changes and `git commit -m "Your message here"` to commit your changes to the master branch
6) Check the online version to make sure your changes have been recorded
7) Run `git pull` to update to latest version

### Tips 

- If there is an error try running `git add *` to resolve it
- Webstorm can handle git/Github instead and includes UI elements which may make your life easier

#Webstorm
Webstorm is the Webdev IDE that we use because it is free to students and fully-featured.

Install by going to https://www.jetbrains.com/student/ and using your *Chapman email* to create an account. Then download and sign in to use for free.

Inside Webstorm use **Check out from Version Control** and sign into Github to automatically clone and manage a project. 

![](/Pictures/filemanager.png) 
The left column shows the open project's file-system

![](/Pictures/edit.png)
The right area is where files are edited and closed

![](/Pictures/events.png) 

The bottom will sometime have a pop-up that gives errors and other info about the project

## Webstorm VCS

The **VCS** menu also can manage the project's version
Use the **Commit** sub-menu option to see all the files being commited, individual changes, and add a message there too.
Don't forget to use **VCS > Update Project** to get the most recent files

# Learning Webdev
Individual projects will use different libraries and support tools, but they all share the central pillars of a webpage.

- HTML is the backbone and structural component of the site. It gives layout and links documents together
- CSS is the styling of a site and makes it look good
- Javascript is the functional part of a site and provides features that HTML  and CSS cannot

### Tips
- Right-click > **Inspect** is extremely valuable for webdev. From the dev tools HTML can be viewed, and CSS can be de-bugged. For example the selected element's padding, margins etc can be seen with the box-viewer. The Javascript console is also available.
![](/Pictures/viewCss.png)
- Don't forget to Google 'css thing' if you're unsure of what to do. There are many resources available online to learn 
- If the website is not updating to changes, **Inspect > Network > check Disable Cache** and also cleat Chrome's cache in Settings 
