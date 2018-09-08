# Filesystem Navigation

## mkdir ( make directory/ies )

creates a directory with specified name

`mkdir directoryName` ( creates directoryName in current directory )

For this session let's create a folder/directory in "Documents" folder to mess around with

<br>

_Try it out_

-   `cd ~/Documents`
-   `pwd` ( to make sure you're in the correct place - this should be `/Users/{your_username}/Documents` - `{your_username}` for me it's `k.ramdany` )
-   `mkdir cliTutorial`
-   `cd` to newly created folder
-   `pwd` ( again make sure you're in the correct folder - this should be `/Users/{your_username}/Documents/cliTutorial` )

<br>

_Try it out_

-   In cli create another folder called `This is a test folder`
-   This actually creates 5 folders!
-   Create folders with spaces in name by quoting, `mkdir "This is a test folder"`
-   However, generally we try to avoid creating folder with spaces in the name for this reason

## rmdir ( remove directory/ies )

Deletes specified empty folders
rmdir directory

Warning: This is permanent, it doesn't go to Trash/Recycle Bin ( like using shift + delete )
!Make sure you're in the correct folder before doing the demo! ( Just in case )

<br>

_Try it out_

-   Use `ls -G` to list folders
-   `rmdir "This is a test folder"`
-   remove all other directories in one command

## touch ( create file )

Creates file with specified name if doesn't exist

`touch filename` ( creates file in current directory )

`touch path/to/directory/filename` ( can directly create files in other directories )

<br>

_Try it out_

-   `touch file`
-   `mkdir tempFolder`
-   `touch tempFolder/file`
-   `touch 1 2 3`
-   `ls -p` ( to see what you have created )

If file exists it just updates file's modified time

## rm ( delete files )

Deletes specified files

`rm file`

`rm file1 file2`

Warning: This is permanent, it doesn't go to Trash/Recycle Bin ( like using shift + delete )
!Make sure you're in the correct folder before doing the demo! ( Just in case )

<br>

_Try it out_

-   `rm 1`
-   `rm 2 3`

## mv ( move and/or rename )

### rename files/folders

<br>

_Try it out_

-   `mv file file2` ( rename files )
-   `mv tempFolder/ folder/` ( rename folders - trailing slash isn't necessary however )

### move files/folders

`mv file folder/` (move file into folder )

`mv folder1/ folder2/` ( move folder1 into folder2 )

`mv file1 file2 folder1/ folder2/ destinationFolder/` ( move files and folders into destinationFolder )

So if you want to rename a folder you have to make sure that the name doesn't already exist

<br>

_Try it out_

-   `mv file2 folder/`
-   `ls folder/`
-   `cd folder` ( for the next task )
-   `pwd` should be `/Users/{your_username}/Documents/cliTutorial/folder`

### mv -i (move interactive)

Be careful with `mv` however, it is a destructive command

Eg:

-   `file1` has content
-   `mv file2 file1` ( this overwrites file1 )

<br>

_Try it out_

-   `mv -i file file2` ( this will prompt if it would cause an overwrite - press `n` )
-   `mv -i file file1` ( no prompt as 2 doesn't exist )

## cp (copy)

### copy files

`cp existingFile copiedFile`

<br>

_Try it out_

-   `cp file1 copied1`
-   `ls` ( check )
-   `cd ..` ( for the next task )
-   `pwd` should be `/Users/{your_username}/Documents/cliTutorial`

### copy folders

`cp -R existingFolder copiedFolder`

<br>

_Try it out_

-   `cp folder/ copiedFolder` trying without flag results in an error
-   `cp -R folder/ copiedFolder` ( copy folder )
-   `ls` ( see the copied folder )
-   `ls folder` ( see contents )
-   `ls copiedFolder` ( see that contents have also been copied )

What if the folder we are copying to already exists?
<br>

_Try it out_

-   `mkdir copiedContents`
-   `cp -R folder/ copiedContents`
-   `ls folder` ( contents of temp get copied into folder )
-   `mkdir copiedFolderInside`
-   `cp -R folder copiedFolderInside` ( note that there is no trailing slash )
-   `ls copiedFolderInside` ( temp folder get copied into folder2 )
-   `cd folder` ( for next task )
-   `pwd` should be `/Users/{your_username}/Documents/cliTutorial/folder`

### cp -i (copy interactive)

As with `mv`, be careful with `cp`, it is also a destructive command

Eg:

-   `file1` has content
-   `cp file2 file1` ( this overwrites file1 )

<br>

_Try it out_

-   `cp -i file1 copied1` ( this will prompt if it would cause an overwrite)
-   `cp -i file1 copied2` ( no prompt as 2 doesn't exist )
-   `cd ..` ( for next task )
-   `pwd` should be `/Users/{your_username}/Documents/cliTutorial`

This is the same when copying folders so be careful!

## rm -r (remove folder and contents)

_Try_

-   `rmdir folder`

`rmdir` doesn't work when folder not empty

<br>

_Try it out_

-   `rm -r folder`
-   `ls`

sometimes you see it as `rm -rf`, the f (force) flag overrides any prompts that may show up

## rm -i ( remove interactive )

_Try it out_

-   cd copiedFolder
-   rm -i file1 ( say no at prompt )
-   rm -i file1 file2 ( choose either at prompt )

## Trash

One thing that I would highly recommend is to actually never use `rm`!
It is almost guaranteed that at one point you will delete something that you actually needed

Download trash (with brew) and use that instead. [_Guide to installing homebrew_](homebrew.md)

It works the same way as finder, where deletion sends files to the trash
Space is not a limiting factor on your macs, and you can routinely tidy it up at a later time

`brew install trash`

You need to have finder open for it to work

Another nice benefit is that it is the same command for files and folders

| [Next (Additional Commands)](Additional.md) | [Home](Intro.md) |
| ------------------------------------------- | ---------------- |
