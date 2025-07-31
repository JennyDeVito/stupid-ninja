# BASH COMMANDS

## General bash commands
clear the terminal srcreen
        
        CTRL + l

you can also type:

        clear


shows the history of commands you typed onto the terminal:

        history

## Navigating through directories
shows in which directory you are: 

        pwd


enter in a directory:

        cd directory-name   


comes back to the last visited directory:

        cd -


goes to the home directory:

        cd ~


comes back one level directory:

        cd ..


## Manipulating Directories
making a directory:

        mkdir Path/DirectoryName


allows to create a long path of directories in one command:

        mkdir -p Directory1/Directory2/Directory3/Directory4


deleting a empty directory

        rmdir DirectoryName


deleting a path of empty directories

        rm dir -p Directory1/Directory2/Directory3/Directory4


## Listing files and directories
lists the common files in the directory:

        ls


lists all the files in the directory:

        ls -a


lists files and directories without the . (current) and ..(previous) folders:

        ls -A


lists files and directories without the backup~ files:

        ls -B


just show the files, without any classification:

        ls -f


lists, classifies and uses symbols to differenciate the files by type:

        ls -F
        ls -F --color=auto (to view types by color)


lists, classifies and uses / do differenciate the directories: 

        ls -p


lists by creation date: 

        ls -t


lists by reverse creation date: 

        ls -tr


long list of files and directories with owner, group owner, filesize, 
permission, modification date:

        ls -l


long list of files and directories with owner, group owner, filesize, 
permission, modification date, current and previous directory and 
hidden files:

        ls -la


long list with only the DirectoryName's attributes: 

        ls -l DirectoryName -d


long list of files with the symbolic link as the same size as the original 
file:

        ls -l -L


long list of files with only the owner column of the files:

        ls -l -o


long list of files with only the group owner column of the files:

        ls -l -g

long list of files and directories with owner, group owner, filesize, 
permission, modification date, current and previous directory and hidden
files:

        ls -lha
        ls -alh


long list of files and directories w/ hidden files classified by creation date:

        ls -laX


lists files in the current folder and also at all the subfolders at the same time

        ls -laR

usefull for finding system logs:
(long list w/ hidden files in reverse creation date order)

        ls -latr


lists files and directories with owner and group owner converted to numbers,
filesize, permission, modification date, current and previous directory and
hidden files:

        ls -ln

## Accessing the root user ~super user~
it will ask for the root user password 

        su -


## Utilities
lists drives and partitions

        df -h