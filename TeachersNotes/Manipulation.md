# Filesystem Navigation

## mkdir ( make directory/ies )

...

-   However, generally we try to avoid creating folder with spaces in the name for this reason

_TeacherNote:_ `ls -Gp` to show that This is a test folder is one folder

## rmdir ( remove directory/ies )

...

-   remove all other directories in one command

_TeacherNote:_ ask how to check if all folders deleted

## touch ( create file )

...

If file exists it just updates file's modified time

_TeacherNote:_

-   show example of above `ls -lT` before and after running `touch`
-   can also use `tree` to show nested files

## mv ( move and/or rename )

_TeacherNote:_ At this point use a shell session with `.bash_profile` loaded with prompt showing folder location and add trailing slash to directories.

```
cd
mv .bash_profilePause .bash_profile
```

Adding something along the lines of the following

```
export PS1="\w $ "
alias ls='ls -pG'
```

### rename files/folders

...

So if you want to rename a folder you have to make sure that the name doesn't already exist

_TeacherNote:_ show example trying to rename a folder with name that already exists

...

### mv -i (move interactive)

...

-   `mv file2 file1` ( this overwrites file1 )

_TeacherNote:_ Add some content to `file2` and `file` to demonstrate overwriting

```
~/Documents/cliTutorial/folder $ ls
file   file2
~/Documents/cliTutorial/folder $ echo 'file stuffs' > file
~/Documents/cliTutorial/folder $ echo 'file 2 things' > file2
~/Documents/cliTutorial/folder $ cat file file2
file stuffs
file 2 things
~/Documents/cliTutorial/folder $ mv file file2
~/Documents/cliTutorial/folder $ cat file file2
cat: file: No such file or directory
file stuffs
~/Documents/cliTutorial/folder $ ls
file2
~/Documents/cliTutorial/folder $
```

...

### copy folders

...

-   `ls copiedFolder` ( see that contents have also been copied )

_TeacherNote:_ `cp -r` does essentially the same thing but doesn't work correctly with links

...

### cp -i (copy interactive)

...

-   `cp file2 file1` ( this overwrites file1 )

_TeacherNote:_ Add some content to `file` and `copied1` to demonstration copy overwriting

```
~/Documents/cliTutorial/folder $ ls
copied1 file   file2
~/Documents/cliTutorial/folder $ echo 'file 1 stuffs' > file1
~/Documents/cliTutorial/folder $ echo 'file 2 things' > file2
~/Documents/cliTutorial/folder $ cat file1 file2
file 1 stuffs
file 2 things
~/Documents/cliTutorial/folder $ cp file1 file2
~/Documents/cliTutorial/folder $ cat file1 file2
file 1 stuffs
file 1 stuffs
~/Documents/cliTutorial/folder $ ls
copied1  file1    file2
```

...

This is the same when copying folders so be careful!

_TeacherNote:_ show interactive option with folders

```
cd ~/Documents/cliTutorial
cp -Ri folder/ copiedFolder
```

...

## Trash

...

Another nice benefit is that it is the same command for files and folders

_TeacherNote:_ show example of using Trash with and without Finder open

```
~/Documents/cliTutorial/copiedFolder $ trash copied1
trash: error -600
~/Documents/cliTutorial/copiedFolder $ trash copied1
~/Documents/cliTutorial/copiedFolder $ cd ..
~/Documents/cliTutorial $ ls
copiedContents/     copiedFolder/       copiedFolderInside/
~/Documents/cliTutorial $ tree
.
├── copiedContents
│   ├── copied1
│   ├── file1
│   └── file2
├── copiedFolder
│   └── copied2
└── copiedFolderInside
    └── folder
        ├── copied1
        ├── file1
        └── file2

4 directories, 7 files
~/Documents/cliTutorial $ trash copiedFolderInside/
~/Documents/cliTutorial $ ls ~/.Trash/ | grep 'copied'
copied1
copiedFolderInside/
~/Documents/cliTutorial $ open ~/.Trash/

right click `copied1` and select `Put Back`
```
