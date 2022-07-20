---
layout: default
title: 5B Verify homograph numbers
parent: 5 Toolbox/FLEx Adjustments
nav_order: 20
permalink: /docs/05-toolboxflex-adjustments/b-verify-homograph-numbers/
---
# 5B Verify homograph numbers

- In Toolbox, it is challenging to get homograph numbers right.
- Yet they matter if we will be validating cross references.
- This page describes a script that can verify homograph numbers.

- Check homograph numbers with the script [add_hm.pl](https://github.com/sil-dictionary-lexical-services/AddHomographs/blob/master/add_hm.pl)
- This script reports if there are duplicate or missing homograph numbers.
- It adds homograph numbers to entries that need them (starting just after the highest number that exists for that entry, even if the existing numbers are not contiguous).
- TODO: So far it does not check subentries to see if they are homographs.  User needs to use some other means to find out if any subentries are homographs of other entries or of Lexeme Forms, and if so, process them manually.
  - The following recipe reports all matches between subentries and \lx:
```bash
perl -CSD -pf opl.pl MyDatabase.db | grep -P '\\lx ([^#]+).*?\\se \1' > Subentry-Homographs
```
To use this, you need to first download the opl.pl script from [Opl_DeOplStub/Piped/opl.pl](https://github.com/sil-dictionary-lexical-services/Opl_DeOplStub/blob/master/Piped/opl.pl) and put it in the same directory as your data file.

- Sense numbers should also be validated.
