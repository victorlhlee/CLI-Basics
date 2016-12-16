# CLI Basics

## Basic Commands
Let's read about a couple of the most common commands that you're going to use.

`ls` = "list directory"; lists all files and folders in the present working directory (where you currently are).

`pwd` = "present working directory"; tells you where you currently are!

`cd foldername` = "change directory"; switches to the directory named 'foldername'. 'foldername' is always a child of the __pwd__ (present working directory). 

`cd ..` =  changes directory to parent of __pwd__. 

`cd ~` = changes directory to user's home directory. Very useful for resetting if you get lost!

`mkdir foldername` = "make directory"; creates a directory named 'foldername'. When you make directory this way, the new 'foldername' directory will be located inside of the __pwd__.

`touch filename.ext` = create a new file of name 'filename' and type '.ext'.

## Step One: Try It Out!
The best way to learn the command line is to __use the command line__! Let's practice a bit to get you settled. First, open your terminal (iTerm2 if you use a Mac or GitBash if you use a Windows PC). Use the `pwd` command to determine your present working directory.

Our first goal is create a `DevLeague` folder on your desktop using the command line. First you need to navigate to the desktop from the command line. Typically there is a "desktop" or "Desktop" folder in user's home directory (__remember__: in command line, capitalization and spelling matters a lot!). Navigate to the user's home directory using `cd ~` and then use `ls` to check for a desktop folder. When you find it, navigate into it using the appropriate `cd` command.

As a general rule, it is a good idea to use list command, `ls`, whenever you enter a new directory so that you can see what you're working with. From inside of your desktop directory, use the list command to see what is on your desktop. Clean as a whistle or got a lot of junk?

Let's create a new "DevLeague" directory using the `mkdir` command, then use the list command to confirm that the new folder was created. Move into the new DevLeague directory using the change directory command.

## Step Two: Build a New Project Base
Our next goal is build the base files for a new project. It will have the following structure:
```
Project Home Directory
│
├── js
│    └── app.js
│
├── css
│    └── styles.css
│
└── index.html
```

Let's begin by running `cd ~`...

Okay! You're back in your user home directory. This is a test! Navigate back to your DevLeague folder using the change directory command.

> HINT: if you type fast and keep misspelling, use [TAB]-complete in order to autocomplete what you need. For example, from your desktop directory, type `cd De` and then hit tab! The terminal will either auto-complete "DevLeague" or give you all options that start with `De`, from which you can type further.

#### Create Project Directory
"cli-basics" will be the name of our new project. From the DevLeague directory, use the make directory command, `mkdir`, to create a new directory named "cli-basics". Use the list command to confirm the folder's creation, then use the change directory command to enter the folder.

#### Create Multiple Folders At Once
Now we are finally ready to create our base files! First, let's create the two folders, "js" and "css", which will store our javascript and CSS files, respectively. One cool thing about the make directory command is that you can create several folders at once by separating each folder name with a space. Run `mkdir js css` and then the list command to see both folders!

#### Create Files
In order to create a __file__ (as opposed to a directory), we use the `touch` command. `touch` works just like `mkdir`, except that it creates files instead of folders. Because it is used to create files, we must remember to include the file type via the extension.

From the project's home directory (`.../cli-basics/`), use the touch command to create an `index.html` file. Use the list command to confirm that the file was created.

You can create __nested__ files. Run `touch js/app.js`. Even though you are in the project home directory, you created a file in the child `js` folder! Use the change directory command to enter the `js` folder, then use the list command to confirm that the `app.js` file was created. Use the change directory command to return to the project home directory. Use the touch command to create `styles.css` in the `css` folder. 

BONUS: Even if you were inside of `.../cli-basics/js/`, you could still create the `styles.css` file inside of `.../cli-basics/css/`... can you figure out how?

## Step 3: Commit Your Work!
Generally, it is best practice to commit your work every few tasks. With all of our basic files and folders created, now is a good time to add, commit, and push our work to GitHub.

__First__, we do need to create a repo through the GitHub interface. Log into GitHub and create a new repository named "cli-basics". 

__Second__, return to the command line and go through the following steps.  
1. `pwd`: make sure that you are in the project home directory (`.../cli-basics/`).  
2. `git init`: this initializes the current directory (and its children) as trackable with git.  
3. `git status`: this shows the current tracking status of local files.  
4. `git add [filename, ...]`: this adds the named files to git staging, from which they can be committed. Run `git add index.html` to add the `index.html` to git staging. Run `git status` again and you should see the notice has changed. Now add __all__ remaining untracked files to git staging.  
5. `git commit -m "enter a message here"`: this commits the staged files. The `-m` is a "message" flag, followed by the message you want to send to remember what was committed. Enter something like "created project base files". After you have committed your files, run `git status` again to see the new notification.  
6. `git remote add origin git@github.com:USER/REPO.git`: this connects your __local__ project to the __remote__ GitHub repository. Replace "USER" with your GitHub username and "REPO" with your remote repository name (in this case, "cli-basics").  
7. `git push origin master`: this pushes your previously-committed work to the origin master branch. Now that these are connected, in future commits you can use simply `git push`. We will discuss using different branches later in the course.  
8. Run `git status` one last time to see the new notification. Are you caught up to origin master and working with a clean directory?  
