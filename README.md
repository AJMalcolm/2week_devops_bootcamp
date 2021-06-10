# DevOps BootCamp

## Introduction to DevOps and why DevOps/benefits

-
-
-
-
-

### Linux commands thata also work on Bash
- Create a Directory `mkdir name_of_the_directory`
- Go inside the Directory `cd name_of_the_directory`
- Come out of the Directory `cd ..` (up 1 level) or `cd` (root directory)
- Who am I `uname -a`
- Where am I? `pwd`
- Create a file `touch name_of_the_file` or `nano file_name` you land inside the file
- Exit from nano `ctrl x` then `y`
- List all `ls -a` (inc hidden files) or `ls`
- Clear the screen `clear`
- Print the contents of a file `cat name_of_file`

- Delete a folder `rm -rf name_of_the_folder`
- Delete a file `rm name_of_the_file`
- Delete multiple files within a directory `rm directory/*`
	- `rm directory/* --dry-run` will return a list of what would be deleted as a result of this command.
	- `rm -v !("file_not_to_be_deleted")` removes all but specified file

- Open Linux Task Manager `top`, `q` to exit this mode
- Similar to above -> `ps`, `ps aux`
- Change user to root `sudo su`, `exit` to escape this. Allows the running of commands without the 'sudo' preface
- Print all commands entered as current user `history`
- Check the status of a program `systemctl status {program}`
- Stops the specified program from running `systemctl stop {program}`

- Run a script file (.sh) `sudo bash name_of_file`

or

- Create an exectutable from a script file `sudo chmod +x name_of_file`, chmod changes the permissions of the file
- Run the executable file `sudo ./provision.sh`



- Create script file:

```
#!/bin/bash

sudo apt-get update -y

sudo apt-get upgrade -y

sudo apt-get install nginx -y

sudo systemctl restart nginx
```

## Running 'app'

navigate into the app folder (move app to vagrantfile location and add to vagrantfile (nano))

if these files/folders are editted, the vagrant will have to be reloaded/ destroyed+up for the changes to take effect. `vagrant reload` is much faster but does not always work. `vagrant destroy` is a clean slate and requires re-update/installation when a new `vagrant up` is run.

`sudo apt-get install nodejs -y`

`sudo apt-get install npm-y`

`sudo apt-get install python-software-properties`

`curl -sL https://deb.nodesource.com/setup_6.x | sudo -E bash -`

`sudo apt-get install nodejs -y`

`sudo npm install pm2 -g` (-g = global access/permissions)

`npm install`

`node app.js`

navigate to `192.168.10.100:3000` to check it is working

to exit the app, `ctrl c` will close it

## Environment Variables

 - How can we check the existing evn var in our system `printevn` or `env`
 - How can we create an Env variable `export name_of_the_var=value`
 - `~/.bashrc`, `~/.profile`, `~/.bash_profile`






























## Permissions

Linux permissions dictate 3 things you may do with a file, read, write and execute. They are referred to in Linux by a single letter each.

__r__ (read) - you may view the contents of the file.
__w__ (write) - you may change the contents of the file.
__x__ (execute) - you may execute or run the file if it is a program or script.

For every file we define 3 sets of people for whom we may specify permissions.

#### Owner

The user who owns the file. Typically the person who created the file but ownership can be changed.

#### Group

Every file belongs to a single group. Groups can have many users in it so you can give access to multiple people.

#### Others

Everyone else who is not in the group or the owner.
Three persmissions and three groups of people. That's about all there is to permissions really. Now let's see how we can view and change them.



### View Permissions

To view permissions for a file we use the long listing option for the command ls.
ls -l [path]

### Change Permissions

To change permissions on a file or directory we use a command called "chmod" It stands for change file mode bits which is a bit of a mouthfull but think of the mode bits as the permission indicators.

```
chmod [permissions] [path]
```

chmod has permission arguments that are made up of 3 components
There are two ways you can use chmod and you will see both used. One is shorter and one is more descriptive.
