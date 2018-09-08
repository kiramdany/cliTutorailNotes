# Additional Commands

## cat (concatenate)

puts entire contents of file to terminal

historically used to put the contents of many files together hence the name

_Try it out_

-   download [this example file](https://raw.githubusercontent.com/kiramdany/cliTutorialNotes/master/Tutorial/example.json)
-   `cd ~/Downloads`
-   `cat example.json`

## less

also a way to view text files

-   / to forward search
-   n for next match
-   N previous match
-   add -I flag to make searches case insensitive
-   q to quit

_Try it out_

-   `less example.json`
-   Find city
-   Find Login details

## globbing

`*` matches as many characters as it can

`?` matches one character

E.g

-   `mv *.png *.jpg *.jpeg images/` - moves all image files into an images folder
-   `mv 2018-09-??.txt september/` - moves all relevant text files into september folder

_Try it out_

-   `cd ~/Documents/cliTutorial/copiedContents`
-   `mkdir 1files`
-   `mv *1 1files`
-   `mkdir otherFiles`
-   `mv file? otherFiles`

## man (manual)

provides information about the certain command

uses the same syntax as less for searching and quitting

E.g

-   `man ls` - can read about the different flags for example

## --help

Some commands have built in flag this gives a similar output to man

E.g

-   `git stash --help`

| [Next (Useful Tips)](UsefulTips.md) | [Home](Intro.md) |
| ----------------------------------- | ---------------- |
