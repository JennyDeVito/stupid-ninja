<!-- @format -->

# BASH COMMANDS

## First things first

Always use `TAB`: it will autocomplete your commands, filenames and directory names. It's a true lifesaver.

`*` are a important wildcard and will help you when searching through

## General bash commands

Clear the terminal srcreen: `CTRL + l`

You can also type:

```bash
clear
```

Shows the history of commands you typed onto the terminal:

```bash
history
```

Accessing the root user _super user_ it will ask for the root user password

```bash
su -
```

Lists drives and partitions

```bash
df -h
```

## Navigating through directories

Shows in which directory you are:

```bash
pwd
```

Enter in a directory:

```bash
cd directory-name/
cd Path/DirectoryName/
```

Go back to the last visited directory:

```bash
cd -
```

Go to the home directory:

```bash
cd ~
```

Comes back in one level of directory:

```bash
cd ..
```

## Listing files and directories

Lists the common files in the directory:

```bash
ls
```

Lists all the content of the directory:

```bash
ls -a
```

Lists the content of the directory without the . (current) and ..(previous) folders:

```bash
ls -A
```

Lists the content without the backup~ files:

```bash
ls -B
```

Just show the content, without any classification:

```bash
ls -f
```

Lists, classifies and uses symbols to differenciate the content by type:

```bash
ls -F
ls -F --color=auto
```

Lists, classifies and uses / do differenciate the directories from other files:

```bash
ls -p
```

Lists by creation date:

```bash
ls -t
```

Lists by creation date: descending:

```bash
ls -tr
```

Long list of files and directories with owner, group owner, filesize,
permission, modification date:

```bash
ls -l
```

Long list of files and directories with owner, group owner, filesize,
permission, modification date, current and previous directory and
hidden files:

```bash
ls -la
```

Long list of files and directories with owner, group owner, filesize,
permission, modification date, current and previous directory and
hidden files - classified by creation date:

```bash
ls -lac
```

Long list with only the DirectoryName's attributes:

```bash
ls -l DirectoryName -d
```

Long list of files with the symbolic link as the same size as the original
file:

````bash
ls -l -L

Long list of files with only the owner column of the files:
```bash
ls -l -o
````

Long list of files with only the group owner column of the files:

```bash
ls -l -g
```

Long list of files and directories with owner, group owner, filesize,
permission, modification date, current and previous directory and hidden
files:

```bash
ls -lha
ls -alh
```

Long list of files and directories w/ hidden files classified by file extension:

```bash
ls -laX
```

Lists files in the current folder and also at all the subfolders at the same time

```bash
ls -laR
```

Usefull for finding system logs:
(long list w/ hidden files in reverse creation date order)

```bash
ls -latr
```

Lists files and directories with owner and group owner converted to numbers,
filesize, permission, modification date, current and previous directory and
hidden files:

```bash
ls -ln
```

## Creating/Deleting Directories

New directory:

```bash
mkdir Path/DirectoryName/
```

Allows to create a long path of directories in one command:

```bash
mkdir -p Directory1/Directory2/Directory3/Directory4/
```

Deleting a empty directory

```bash
rmdir DirectoryName
```

Deleting a path of empty directories

```bash
rmdir -p Directory1/Directory2/Directory3/Directory4
```

## Manipulating files

### Printing the content of a file (cat)

Shows the content of a file:

```bash
cat filename
cat Path/filename
```

Shows the content of a file with numbered lines (inclunding blank lines):

```bash
cat -n filename
cat -n Path/filename
```

Shows the content of a file with numbered lines (without blank lines):

```bash
cat -b filename
cat -b Path/filename
```

Shows the content of a file hidding repeated blank lines (shows only one):

```bash
cat -s filename
cat -s Path/filename
```

Shows the content of a file adding a $ sign to the end of every line, even the
blank ones:

```bash
cat -E filename
cat -E Path/filename
```

Shows the content of a file with the TAB converted to '^I' character:

```bash
cat -T filename
cat -T Path/filename
```

Shows the content of a compressed file (decompresses it and shows its contents):

```bash
zcat filename.gz
zcat Path/filename.gz

bzcat filename.bz2
bzcat Path/filename.bz2

xzcat filename.xz
xzcat Path/filename.xz
```

Shows the content of a file, descending:

```bash
tac filename
tac Path/filename
```

Shows the content of a file descending and pointing to the \n character:

```bash
tac -s filename
tac -s Path/filename
```

### Removing files (rm)

Remove files normally (one by one) or recursively (like a path of destruction):

```bash
rm filename
rm Path/filename
```

_I'dont understand yet why, but in some configurations (like Debian 11), Bash will ask if you really want to delete the file and give you a y/n option, but, that's not the case in Debian 12, for example._

Remove directories normally (one by one) or recursively (like a path of
destruction):

```bash
rm -r Directory/
```

_I'dont understand yet why, but in some configurations (like Debian 11), Bash will ask if you really want to delete the file and give you a y/n option, but, that's not the case in Debian 12, for example._

Remove, by force, directories recursively (without asking, even if it is
configured to):

```bash
rm -rf Directory/
```

Remove a file:

```bash
rm -f filename
rm -f Path/filename
```

Remove a hidden file:

```bash
rm -f .filename
rm -f Path/.filename
```

If you want a confirmation before removing a file or a directory:

```bash
rm -i filename
rm -i Path/filename
rm -r -i Directory/
```

_Using the -i option it will ask for a confirmation for sure. In Debian 11, 12 and also Linux Mint Xia._

Remove all non hidden files and directories inside a directory:

```bash
rm -rf *
```

### Copying files (cp)

Copies a file (or multiple files) to another file or a directory:

```bash
cp [origin] [destination]
cp file_to_copy destination_file
cp file_to_copy_1 file_to_copy_2 file_to_copy_2 [...] Path/destination_directory
```

- _[origin] and [destination], in that case can also be a path._
- _When copying multiple files, the destination **must** be a directory._

Copy all the files in a directory to another one:

```bash
cp * Path/destination_directory
```

Copy all the files and directories in a directory to another one:

```bash
cp -r * Path/destination_directory
```

_It won't copy itself - like one of the directories to copy is the destination directory._

Copy a file, by force:

```bash
cp -f file_to_copy [destination]
```

_[destination] can be another file or a directory._

Copy a directory, by force:

```bash
cp -fr Path/directory_to_copy Path/destination_directory
```

To see the copy operations running, you can use the -v operand along with
your commands:

```bash
cp -v Path/directory_to_copy Path/destination_directory
cp -vfr Path/directory_to_copy Path/destination_directory
```

Copy the special devices, sockets and all different kinds of files and
directories that can be contained in a directory:

```bash
cp -R [origin] [destination]
```

_Try to use, by defaults the -R instead of -r, the -r ignores those devices._

Creates a symbolic link to a file:

```bash
cp -vs [origin] [destination]
```

Only make a copy if the file to be copied is most recent to the file to be replaced:

```bash
cp -vu [origin] [destination]
```

Don't copy files in a different filesystem (and show the operations running `-v`):

```bash
cp -vrx [origin] [destination]
```

Make the copy and preserve the file's attibutes (owner, group owner and
permissions):

```bash
cp -p [origin] [destination]
```

Combines the -d (preserves the symbolic links), -p (preserve the file's
attibutes) and -R (copy the special devices and all different kinds of files
and directories):

```bash
cp -a [origin] [destination]
```

### Moving and/or renaming files (mv)

Move a file to another destination:

```bash
mv [origin] [destination]
mv Path/file_to_be_moved Path/file_to_the_destination
mv file_to_be_moved_1 file_to_be_moved_2 file_to_be_moved_2 [...] Path/destination_directory
```

Interactive way to move a file to another destination:

```bash
mv -i file_to_be_moved Path/destination_directory
```

_Apparently, it doesn't work on Debian 12. It just moved the file without any interaction._

<!-- TODO: test in Linux Mint -->

Change the filename at the same time you make the copy:

```bash
mv Path/file_to_be_moved_OLD_name Path/file_to_destination_NEW_name
```

But, you can also make the name changing in the same directory without moving
the file:

```bash
mv file_old_name file_new_name
```

_I think, the logic is that, by defaults, if the second argument isn't a directory the mv command will rename the file. If, the second argument is a directory the mv command will move the file into that directory._

Move a file, by force:

```bash
mv -f [origin] [destination]
```

Moves only if the file to be moved is newest than the the files that already
exists (if it exists) in the destination folder:

```bash
mv -u [origin] [destination]
```
