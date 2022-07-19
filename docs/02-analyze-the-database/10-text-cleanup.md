---
layout: default
title: 2A Text Cleanup
parent: 2 Analyze the database
nav_order: 10
---
# 2A Text Cleanup
## Line ends
Most of these scripts work better if the files have Unix line endings.  However, there are some steps of the process that either expect Windows line endings, or change the file to have Windows line endings.  Specifically, Solid always writes the file out with Windows line endings, and CC assumes the file has Windows line endings.  If CC runs on a file with Unix line endings, you may end up with a file with mixed line endings, and that could lead to data corruption.   You could also end up with mixed line endings if you apply certain regular expressions.

It is recommended that:
- At the beginning of the process, change the file to use Unix line endings.
- At various stages of the process, periodically check whether the file you are working with still has Unix line endings.  If not, change it back.
- If you have tried running one of these scripts and the output is not what you expect (for instance, there are no changes, or the output is empty, or the script says it can't find any data to run on), check the line endings.
- If you are about to run a CC table over the file, first change the file to Windows line endings, then do the CC process, and then change it back to Unix line endings.
- Before you do the actual import, double check that the file does not have mixed line endings.  (For the import, it doesn't matter if it is Unix or Windows line endings.  What matters is that it is uniform.)

There are several ways to change a file with Windows line endings to Unix line endings.  Here are a few options (you only need to do one or the other):

1. Notepad++
- Open the file in Notepad++
- Use the menu item Edit/EOL Conversion/Unix (LF)
- Save file

2. If you followed the instructions in the Infrastructure section, there should be utilities in your WSL installation called dos2unix and unix2dos.  You can apply these commands in your WSL terminal like this (substitute appropriate filenames):
```bash
dos2unix < MyDatabase.db > MyDatabase-unix.db
```
To change it back to Windows line endings:
```bash
unix2dos < MyDatabase-unix.db > MyDatabase-windows.db
```

## Remove trailing blanks
Before wrapping the lines, remove trailing blanks, to make other line comparisons work better.  One way to do this is in Notepad++.
- Open in Notepad++
- Use  the Replace command, with "Regular Expressions" on
- Find: **[ *$]**  (Leave off the square brackets, and make sure there is a Space before the *)
- Replace with: **[]** (nothing)

## Join lines
All of these scripts assume that each field occurs on only one line.  However, Toolbox allow fields to wrap.  To prepare the Toolbox file, use **joinlines.pl** to unwrap lines:

Download the script [joinlines.pl](https://github.com/sil-dictionary-lexical-services/TextCleanup/blob/master/joinlines.pl)
```bash
perl joinlines.pl < MyDatabase-unix.db > MyDatabase-joined.db
```

This works best if you have removed trailing spaces first.

[Note for those who are comfortable with more than one way to do things:  If you want to change the line ends and unwrap the lines all in one command, you can do this instead:

```bash
perl dos2unix.pl < MyDatabase.db | joinlines.pl > MyDatabase-joined.db
```

However, make sure there are no trailing blanks in the file.  This combination does not apply that step.]
