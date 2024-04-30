# Terminal commands cheat sheet

### Why we need terminal?

1. Makes making a large number of files easier 
2. There are some unique things you can only do in the terminal
3. In the case where we have a server stack, it would be inefficent to have a monitor and GUI for each server. So for efficieny in time and computing power we use the terminal in order to communicate with things like servers.


### Linux and MacOS

MacOS and Linux have a common predecessor which is UNIX so learning terminal commands on the Mac can be transferred to linux based machines.


#### Directories visualised


![alt text](Screenshot 2024-04-30 at 10.09.47.png)

### Terminal basics
Every folder is inside a parent directory e.g. in the above image the file personal_pictures is in the Images folder (so Images is the parent folder for that file). So we need some commands that move up and down the branches of folder paths.

#### What is ~ ?

The ~ symbol signifies we are in the home directory which is the highest point of the directory branch.

| Command | Description of what it does|
| --------- | ------- |
| Control + L| clears the screen by pushing the cursor to the top of the screen|
|clear| clears the previous commands from the screen|
|control + c| This takes you out of any command|

A blue colour will be for folders/directories and files will be white. (This is because of a terminal extension we downloaded)

### Why do some files have a . before them?

A dot before a file name signifies this is a hidden file that ordinary non developers shouldn't be able to see in case of accidental deletion.

#### How to see where you are / what files/folders you have ?
|Command| Description|
| ----- |------------|
| pwd| This stands for present working directory and will print a file path of where you are.|
|ls| This command will print the folders or files that are in the current directory|
|ls -a| This will show all files including ones with .folder_name which are the hidden files.|
|ls -l| This gives extra information about folders/files in the current directory.Extra information includes time of last edit, permissions etc.
|ls -la| This command gives extra information on all files in the current directory, including the hidden files|

A command such as ls with a - is called a flag for that command.

#### Moving/Making folders and files:
|Command|Description|
|-------  |-----------|
|cd| cd stands for changing directory and this command alone takes you back to the home directory|
|  cd folder_name  | This will move to the given folder|
|cd -| Moves you back to the previous directory incase you've accidently moved to the home directory by mistake.|
|cd ..| This will move you up one level in the directory branch (move to the current parent directory)|
|mkdir folder_name| This makes a folder in the current directory you are in|
|touch `file_name.extension_type`| Makes a file in the current directory|
|open name.extension| Opens up the file in a default app|
|open.| This command opens up the file finder tool showing the current folder|
|mv file_name `new_location`| mv stands for move and this moves the selected file to a new folder|
|mv `current_file_name new_final_name`| Renames a file to the new file name|




##### Why do we use snake case for folder and file names?

If we wanted to make make a folder for some reason called my folder. Without snake case:
`mkdir my folder` will make two seperate folders, folder 1 will be called my and folder 2 will be called folder as we are passing mkdir 2 arguemnts.
So doing `mkdir my_folder` will make one folder called my_folder.

#### Deleting files/folders
|Command|Description|
|-------  |-----------|
|rm file_name| rm stands for remove and this removes the file name|
Unlike deleting files in the GUI, there is no recycle bin for deleting files in the terminal.

|Command|Description|
|-------  |-----------|
| rm -r `folder_name`| The -r stands for recursively as folders are deleted in reverse from the deepest part of its respective branch backwards|
|rm -rf `folder_name`| The added f means forcefully which is used to delete protected files.
|rm -rf ~| DO NOT USE THIS COMMAND AS IT REMOVES THE HOME DIRECTORY INCLUDING THE OS and bricks the machine.|

#### Copying files/folders
|Command|Description|
|-------  |-----------|
|cp `file_name new_location`| copies a file to a ew place|
|cp -r `folder_name new_location`| The -r flag is needed as folders are copied reversly|

#### Autocompleting 
The terminal extension downloaded allows us to press tab when typing in a file/folder name for it to autocomplete. And use tab again to cycle through the options.

## Git/Github
### What is Centralised version control?

There are centralised version control systems such as subversion, CVS. The idea behind a centralised version control system is all the files are stored in a server (most likely an internal server).
You don't store a complete copy of the project files locally. Its a simple push/pull model. When pulling a file and working on it, no one else can work on that file until its pushed back to the server.
Needs to be connected to a network at all times.

### What is Decentralised Version Control
Git is an example of a DVCS

The difference between Git and other DCVS, we store a local copy of the repository (project). We also have a local history of changes that have been made (where each change is a "version" in the history) and each changes are called "commits. 
Can be used without a network connection as files are stored locally.
Github is a cloud service where you store a remote version of the project.

### Using Git in the terminal

|Command|Description|
|-------  |-----------|
|git init| This initilises git to be able to run git commands in the terminal. Don't put this git command in the home directory|

When in the git init repository there are different branches and there is a main branch so git:(main) refers to the main branch.

Untracked files in git are files that aren't in the current repository.

#### Commands to add and stage files to git
|Command|Description|
|-------  |-----------|
|git add `file_name`| adds a file to the staging part of the current repo|
|git add .| Adds all files in the directory to the staging part.
|git status| tells us if files need to be commited.Red means untracked, green means its tracked and in the staging area but not committed yet to the history of the project.|

A git commit is a change made to some code/file i.gite. a version of it.

|Command|Description|
|-------  |-----------|
|git commit -m'red means untracked, green means its tracked and in the staging area but not committed yet to the history of the project.'| Pushes the changes through|
|git log| Shows all the versions that have been made, press Q to exit (Quit)|

After making a change to a file it needs to be re added to the staging area.

#### Reversing a commit
|Command|Description|
|-------  |-----------|
|git revert commit_number| Reverts the commit and opens a code editor, just close the code editor for the commit to go through. The commit_number is obtained in the git log command.|

##### Trouble shooting a commit reversal
|Command|Description|
|-------  |-----------|
| revert --hard| Does a reset so you can then reverse|

##### gitignore files:

These are files/folders which we want to not be pushed in a commit.

Create a text file. Make a git ignore file using git add .gitignore. Open the gitignore file and put the text files name in there.
If you use ls you'll see the ignored text file but in the staging area, the text file won't be there anymore.



