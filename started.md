# Creating Your Enviroment 

# Basic Neccesities 
- Github: https://github.com/UX-Society
- Github Education: https://education.github.com/pack
- Webstorm: https://www.jetbrains.com/webstorm/
- fish (recommended): https://fishshell.com/

### Windows only
- Fedora (recommended): http://linuxbsdos.com/2016/12/01/dual-boot-fedora-25-windows-10-on-a-computer-with-uefi-firmware/ 
- Bash for Windows : https://msdn.microsoft.com/en-us/commandline/wsl/install-win10 (Windows only)

# Setup

Make a github account with your school email and get invited to the UX-Society repository linked. Then use the Github Education link to get free stuff. Also sign up with your school email in Jetbrains to get Webstorm for free (or use an IDE of your choice). Fish is a reccomended shell to replace bash and will make terminal work easier, but is not required.
To use fish either type `fish` in the terminal or set it as defualt with `chsh -s /usr/bin/fish` (needs root)
# Basic Terminal Usage

The ternimal is a powerful way to use a computer and learning how to use it properly important for seroius work. Using the terminal is easy for macOs and other Linux based computers and replacing bash with fish will make it even easier. Windows is not recommended for web-dev work, but bash for Windows can be installed. To use the terminal a command has to be given which follows this general format.
```
    "command name" "command sub-name" -arguments "info"
```
For example:
```
    sudo apt-get install -y fish
```   
To break this command down, it starts with 'sudo' which indicated that the command is being run with max user authorization, use it very carefully. 'apt-get' is the main command and it tell the computer that I want to manage my packages (package is a name for a software bundle, which has been replace by App). 'install' tells the computer that I want to install a package, a feature of apt-get. '-y' is an aurgument denoted by the dash and slightly changes what the computer does, in this case to automatically skip the installation confirmation dialogue. 'fish' is the info of what is being done, in this case the package.

Here are some useful commands:

- cd: 'change directory' - it moves you around the filesystem. Ex:  `cd WebstormProjects/nsu-website/`
- ls: 'list directory contents' - tells you all the files in the current dir. Ex: `ls -a`
- man: 'manual' - tells you how to use a command. Ex: `man man` (tells you how to use itself)
- help: in fish opens documentation for the shell in browser. Ex: `help`
 
# Libraries and Tools

- Webpack: https://webpack.js.org/
- Hugo: https://gohugo.io/
- Sass: http://sass-lang.com/guide
- Yarn or npm: https://yarnpkg.com/en/ or https://www.npmjs.com/

# Installing

This project requries yarn and hugo. Hugo is used to build the site and view a demo of what the site will look like.
Yarn is used to install the node packages such as webpack and lint. These tools help streamline the javascript and css. 

# Getting Started

## Building The Static Stuff

package.json has been configured with some helpers to simplify the build process for building the javascript and the scss files. 
These commands will only work under a director with a package.json file.

- `yarn run build' or 'npm run build`
  - will build from src to public
- `yarn run watch` or `npm run watch`
  - will build and watch for changes in src, but the webpack build has to be running for these changes to update

Building the css and javascript will take in the contents of src and output it to public. Look in the package.json file under scripts
to see where the run commands wire to. for instance `yarn run lint` will run eslint on the codebase.

```
  "scripts": {
    "lint": "eslint .",
    "install_hugo": "brew update && brew install hugo",
    "build": "webpack",
    "watch": "webpack --watch"
  },
  ```
  
To actually preview the site run `hugo server` from the root or the project folder (`cd WebstormProjects/nsu-website/`). This folder should contain a themes folder.
If everything runs correctly this should output in the terminal:

```
WARNING: calling IsSet with unsupported type "invalid" (<nil>) will always return false.


Built site for language en:
0 draft content
0 future content
0 expired content
7 regular pages created
30 other pages created
0 non-page files copied
12 paginator pages created
7 tags created
4 categories created
total in 35 ms
Watching for changes in /home/michaelpollind/project/nsu-website/{data,content,static,themes}
Serving pages from memory
Running in Fast Render Mode. For full rebuilds on change: hugo server --disableFastRender
Web Server is available at http://localhost:1313/ (bind address 127.0.0.1)
```

### Note

you will need to run both the yarn and hugo commands. To do this open another tab in your current terminal or a new terminal. yarn will update the css and hugo should react to the changes from webpack.

# Usage
After running hugo and yarn, view the site by going to http://localhost:1313/. Most of the files in the site can be ignored, the important files and directories to use are laid out here.

- /themes/source-flask-theme/ is the main folder of interest
  - /themes/source-flask-theme/layouts/partials/ is were your section of html to edit will be found
  - /themes/source-flask-theme/src/sass/section/ is where your sass (css) file will be found
  - /themes/source-flask-theme/static/ is where icons should be added
- /static/img/ is where images should be added
- config.toml/ is where the actual info for the site is located.
        Edit your section under `[params."your section name]` and reference this content with `.Site.Params."sub section name"."content name"` in the html partial file
- 
 

Edit these files to chage the website locally and they will be merged with the main branch when done. Tomt changes the actual content (text, images etc.), html changes the elements, and sass (css) changes the layout and appreance of those elements.
 
# FAQ
If you are confused or get and error: 
- just Google it `: )`
- really though, ask Micheal on Slack 


  
  
  
