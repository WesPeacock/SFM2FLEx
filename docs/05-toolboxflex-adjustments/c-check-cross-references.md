---
layout: default
title: 5C Check cross references
parent: 5 Toolbox/FLEx Adjustments
nav_order: 30
permalink: /docs/05-toolboxflex-adjustments/c-check-cross-references/
---
# 5C Check cross references
In Toolbox, references are not required to exist in the database, but in FLEx they are.  If you import an SFM file with references that don't point at something else in the database, you may be surprised or disappointed at the results.  To prevent that, please read the following considerations.

- You can check cross references using the script [check_cf_special.pl](https://github.com/sil-dictionary-lexical-services/CheckCrossRefs/blob/master/check_cf_special.pl)
  - This script uses an .ini file for specifying the input/output files, and also which markers to check.
  - This script reports references without targets.
  - It converts targetless ones to use a different marker (\sy_NF, \cf_NF, etc.).
- When importing, map these to a custom field (e.g., SynonymNotFound, CompareNotFound) so the linguist can easily find them and decide on the best way to fix them.
- Prepare instructions for the linguist, explaining how to filter for non-blanks in these fields, and then adjust the appropriate data.
