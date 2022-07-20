---
layout: default
title: 4 Prepare empty database
has_children: true
nav_order: 40
---
# 4 Prepare empty database
- A. Create an empty database with the appropriate writing systems and make a backup.
  - Instructions on how to choose/set up Writing Systems
  - Set different colors for each (see:[FW-CONFIG 01 Set WS Colors](https://youtu.be/Ht0A7HGybi0).
- B. Populate the Category list with the set of POS established earlier. [Instructions for this are in this submenu](b-populate-the-category-list/)
- C. Create any custom fields that are needed, with appropriate writing systems.
- D. List items
  - Add items to existing lists
  - Create any custom lists
  - (Import a handful of tricky entries?  Try configuring the dictionary?  See if anything else is needed?)
- E. Set up the sort order?  Can be done later as well.

NOTE:  It is good to start this empty database early in the process.  However, as you go through the remaining steps, you will learn more about what needs to be in it.  You will make adjustments and make a new backup of the empty database.  Expect it to be an iterative process:
1. Create the empty database
2. Make your best guess for the Writing systems, formatting, custom fields that will be needed.
3. Proceed with more steps in the import process.
4. When you discover something new that needs to be in the empty database, add it.  Make a new empty backup, with a suitable comment (e.g., "AddedMorePOS" or "AddedCustFlds").
5. Repeat steps 3 and 4 until you are almost ready to try an import.
6. Do a trial import.  Look at the results.  Make a note of what should have been different in the empty database, and anything else you need to do.
7. Restore the most recent version of the empty database.  Allow this to overwrite your import--this will delete the imported version.  (Alternatively: you could delete the project before you restore the empty version.)  Make the needed changes in this restored empty version.  Make another backup of this newly revised empty database, with a suitable comment.
8. Do any further steps that are needed to the SFM file.
9. Repeat steps 6-8 as needed.
