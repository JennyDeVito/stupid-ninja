# BASH COMMANDS

## General bash commands

Clear the terminal srcreen

        CTRL + l

You can also type:

        clear

Shows the history of commands you typed onto the terminal:

        history

## Navigating through directories

Shows in which directory you are:

        pwd

Enter in a directory:

        cd directory-name
        cd Path/DirectoryName

Comes back to the last visited directory:

        cd -

Goes to the home directory:

        cd ~

Comes back in one level of directory:

        cd ..

## Manipulating Directories

Making a directory:

        mkdir Path/DirectoryName

Allows to create a long path of directories in one command:

        mkdir -p Directory1/Directory2/Directory3/Directory4

Deleting a empty directory

        rmdir DirectoryName

Deleting a path of empty directories

        rmdir -p Directory1/Directory2/Directory3/Directory4

## Listing files and directories

Lists the common files in the directory:

        ls

Lists all the files in the directory:

        ls -a

Lists files and directories without the . (current) and ..(previous) folders:

        ls -A

Lists files and directories without the backup~ files:

        ls -B

Just show the files, without any classification:

        ls -f

Lists, classifies and uses symbols to differenciate the files by type:

        ls -F
        ls -F --color=auto (to view types by color)

Lists, classifies and uses / do differenciate the directories:

        ls -p

Lists by creation date:

        ls -t

Lists by reverse creation date:

        ls -tr

Long list of files and directories with owner, group owner, filesize,
permission, modification date:

        ls -l

Long list of files and directories with owner, group owner, filesize,
permission, modification date, current and previous directory and
hidden files:

        ls -la

Long list of files and directories with owner, group owner, filesize,
permission, modification date, current and previous directory and
hidden files - classified by creation date:

        ls -lac

Long list with only the DirectoryName's attributes:

        ls -l DirectoryName -d

Long list of files with the symbolic link as the same size as the original
file:

        ls -l -L

Long list of files with only the owner column of the files:

        ls -l -o

Long list of files with only the group owner column of the files:

        ls -l -g

Long list of files and directories with owner, group owner, filesize,
permission, modification date, current and previous directory and hidden
files:

        ls -lha
        ls -alh

Long list of files and directories w/ hidden files classified by file extension:

        ls -laX

Lists files in the current folder and also at all the subfolders at the same time

        ls -laR

Usefull for finding system logs:
(long list w/ hidden files in reverse creation date order)

        ls -latr

Lists files and directories with owner and group owner converted to numbers,
filesize, permission, modification date, current and previous directory and
hidden files:

        ls -ln

## Accessing the root user ~super user~

it will ask for the root user password

        su -

## Utilities

Lists drives and partitions

        df -h

## Manipulating files

### Viewing the content of a file (cat)

Shows the content of a file:

        cat filename
        cat Path/filename

Shows the content of a file with numbered lines (inclunding blank lines):

        cat -n filename
        cat -n Path/filename

Shows the content of a file with numbered lines (excluding blank lines):

        cat -b filename
        cat -b Path/filename

Shows the content of a file hidding repeated blank lines (shows only one):

        cat -s filename
        cat -s Path/filename

Shows the content of a file adding a $ sign to the end of every line, even the
blank ones:

        cat -E filename
        cat -E Path/filename

Shows the content of a file with the TAB converted to '^I' character:

        cat -T filename
        cat -T Path/filename

Shows the content of a compressed file (decompresses it and shows its contents):

        zcat filename.gz
        zcat Path/filename.gz

        bzcat filename.bz2
        bzcat Path/filename.bz2

        xzcat filename.xz
        xzcat Path/filename.xz

Shows the content of a file in a upside-down way:

        tac filename
        tac Path/filename

Shows the content of a file in a upside-down way pointing to the \n character:

        tac -s filename
        tac -s Path/filename

### Removing files (rm)

Remove files normally (one by one) or recursively (like a path of destruction):

        rm filename
        rm Path/filename

+ I'dont understand yet why, but in some configurations (like Debian 11), the
Bash will ask if you really want to delete the file and give you a y/n option
But, that's not the case in Debian 12, for example.

Remove directories normally (one by one) or recursively (like a path of
destruction):

        rm -r Directory/

+ I'dont understand yet why, but in some configurations (like Debian 11), the
Bash will ask if you really want to delete the directory and give you a y/n
option. But, that's not the case in Debian 12, for example.

Remove, by force, directories recursively (without asking, even if it is
configured to):

        rm -rf Directory/

Remove a file:

        rm -f filename
        rm -f Path/filename

Remove a hidden file:

        rm -f .filename
        rm -f Path/.filename

If you want a confirmation before removing a file or a directory:

        rm -i filename
        rm -i Path/filename
        rm -r -i Directory/

Remove all non hidden files and directories inside a directory:

        rm -rf *

### Copying files (cp)

Copies a file (or multiple files) to another file or a directory:

        cp [origin] [destination]
        cp file_to_copy destination_file
        cp file_to_copy_1 file_to_copy_2 file_to_copy_2 [...] Path/destination_directory 

+ [origin] and [destination], in that case can also be a path.
+ When copying multiple files, the destination *must* be a directory.

Copy all the files in a directory to another one:

        cp * Path/destination_directory

Copy all the files and directories in a directory to another one:

        cp -r * Path/destination_directory

+ It won't copy itself - like one of the directories to copy is the destination
directory.

Copy a file, by force:

        cp -f file_to_copy [destination]

+ [destination] can be another file or a directory.

Copy a directory, by force:

        cp -fr Path/directory_to_copy Path/destination_directory

To see the copy operations running, you can use the -v operand along with
your commands:

        cp -vfr Path/directory_to_copy Path/destination_directory

Copy the special devices, sockets and all different kinds of files and
directories that can be contained in a directory:

        cp -R [origin] [destination]

+ Try to use, by defaults the -R instead of -r, the -r ignores those devices.

Creates a symbolic link to a file:

        cp -vs [origin] [destination]

Only make a copy if the file to be copied is most recent to the file to be replaced:

        cp -vu [origin] [destination]

Don't copy files in a different filesystem:

        cp -vrx [origin] [destination]

Make the copy and preserve the file's attibutes (owner, group owner and
permissions):

        cp -p [origin] [destination]

Combines the -d (preserves the symbolic links), -p (preserve the file's
attibutes) and -R (copy the special devices and all different kinds of files
and directories):

        cp -a [origin] [destination]

### Moving and renaming files (mv)

Move a file to another destination:

        mv [origin] [destination]
        mv Path/file_to_be_moved Path/file_to_the_destination
        mv file_to_be_moved_1 file_to_be_moved_2 file_to_be_moved_2 [...] Path/destination_directory

Interactive way to move a file to another destination:

        mv -i file_to_be_moved Path/destination_directory

+ Apparently it doesn't work on Debian 12. It just moved the file without any
interaction.

A second and *very useful* feature of the mv command is the option to change
the filename as you make the copy:

        mv Path/file_to_be_moved_OLD_name Path/file_to_destination_NEW_name

But, you can also make the name changing in the same directory without moving
the file:

        mv file_old_name file_new_name

+ The logic is that, by defaults, if the second argument isn't a directory the
mv command will rename my file. If, the second argument is a directory the mv
command will move the file into that directory.

Move a file, by force:

        mv -f [origin] [destination]

Moves only if the file to be moved is newest than the the files that already
exists (if it exists) in the destination folder:

        mv -u [origin] [destination]
