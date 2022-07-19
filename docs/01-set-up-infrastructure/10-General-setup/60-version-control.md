---
layout: default
title: Version Control
parent: 1A General Setup
grand_parent: 1 Set up infrastructure
nav_order: 60
---
# Version Control

Establish an approach for "version control" for the data.
 - Why do we need "version control"?
    - It is helpful to have "breakpoints" as you make different changes to the file.  If you need to "undo" some significant change you made, the easiest thing may be to revert to an earlier stage.
    - It is also important to be able to use a diff tool to compare the "before" and "after" when you make a significant change.  The changes we make are sweeping enough, with enough possible "edge cases", that it is crucial that we validate each one.  You want few enough changes between each version of the file that you could glance over most of the changes.
      - [kdiff3](https://sourceforge.net/projects/kdiff3/files/) is a really helpful visual diff tool
      - There are many others out there; it doesn't matter, as long as you use something.
  - How can we do version control?
    - If you are comfortable with git or other source control software, you can use that.  [Details not posted here, at least not for now.]

    - If you are not comfortable with something like "git", you can mimic that by making a copy of the file every so often, and giving it a new name.  For instance, the first modification of the file might be dictionary-mod01.db.  You will make some edits in that, and then just before you make some other major change, you will copy it to a file called dictionary-mod02.db.  Each time you copy the file to a new name, you will make an entry in your log indicating what change was made between the versions.

    - What "best practices" will help with the "do it yourself" version control?

    - If you are using the "make copies along the way" approach to having breakpoints, at some point you may find that you need to go back to an earlier version of the file.  At that point it is helpful to clear out the files that you made changes to but have not abandoned.  There are several possibilities:
      - You could delete them.
      - You could create a folder called "Pass1" and move them into there.
      - You could make a copy of your entire working directory and begin working over in this new copy.  Before you begin working, delete the files you have abandoned.  The previous copy of the working folder still has them, in case you do need to get them back.  (For instance, you may start out working in a folder called Working-2020.01.05.  After you have done some work, you want to "clear your workspace".  Make a copy of that whole folder and call the new one Working-2020.01.19.  In the new folder delete unwanted files (or start with it empty, and only bring in the ones you want), and then continue working in that folder.
