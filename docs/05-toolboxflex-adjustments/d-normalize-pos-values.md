---
layout: default
title: 5D Normalize POS values
parent: 5 Toolbox/FLEx Adjustments
nav_order: 40
permalink: /docs/05-toolboxflex-adjustments/d-normalize-pos-values/
---
# 5D Normalize POS values
- See if the \ps values need to be normalized
  - Determine the set of values used in \ps by using a recipe like this on a Linux command line (note the space after "ps"):
```bash
egrep "^.ps " MyDatabase.db | sort | uniq -c > pos-list.txt
```
  - (It is easy to modify this "recipe" to find the range of values for any fixed-value field, such as \so or \ue or \bw.  It is helpful for determining whether the field really does use "fixed values" or if it is "free-form".)
- See if there are some values that are not appropriate for importing into FLEx
  - Look for obvious typos (e.g., same abbreviation with init caps or all lowercase, some with periods at the end and others without, one abbreviation spelled more than one way)--you will want to pick one way to make them all consistent.
  - Look for overspecification that may need to be simplified for the Category list in FLEx (e.g, N-masc-inan)
  - This process already assumes that if there are multiple POS in a single field (e.g., "n, adj" or "vt; vi"), then the linguist will need to investigate it further after the import is done--don't worry about those.
- Download and then edit [FixPOS-NNN.pl](https://github.com/sil-dictionary-lexical-services/FixPOS) so it can normalize the SFM file as decided.  (Requires enough understanding of Perl and regular expressions to edit this script.  Get help if you are not confident of this part.)
- If you are finished with moving fields around (e.g., during work with Solid), then go ahead and apply that script.  Otherwise, save it for later.
- Communicate the list to the linguist; see if they want any further changes.
- Communicate the normalized list to those working on the front matter, to be included in the list of abbreviations.
