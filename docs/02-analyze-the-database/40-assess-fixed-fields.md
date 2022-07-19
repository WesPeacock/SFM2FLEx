---
layout: default
title: 2D Assess fixed fields
parent: 2 Analyze the database
nav_order: 40
---
# 2D Assess fixed fields
Some fields have content that has a fixed set of possible values.  It is important to check these fields for consistency before importing, either to normalize the data, or to import it into a field that isn't a list field, if it is actually free-form.  If it is in fact a list, you will want to pre-populate the list in FLEx with the possible values, before you import.  You will do this at a later stage.
 - The most common field that used fixed content is the Part of Speech field (\ps or \pn in MDF).
 - Other fields that may have fixed content include: Usages (\ue), Etymology Source language (\et or \bw), Semantic Domains (\sd), Source (\so).  There may also be others.
 - Once you have determined which ones seem to have fixed content, make a list of all the values that occur for that field in this database.
   - For the \ps field, you can use this command at the command line:
```bash
egrep "^.ps " dictionary.sfm | sort | uniq -c > ps.txt
```
   - The same command can be used for other fields, if you replace both occurrences of "ps" with the other marker.  For instance:
```bash
egrep "^.sd " dictionary.sfm | sort | uniq -c > sd.txt
```
   - Review the list that is in the resulting file (e.g., ps.txt).  See if it is consistent, or if it needs to be normalized, or if it is not in fact list data.
   - For Parts of Speech, a script like Fix-POS-NNN.pl can be used to normalize the data, and do additional operations that are important for an import.
