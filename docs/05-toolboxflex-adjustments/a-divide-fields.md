---
layout: default
title: 5A Divide fields
parent: 5 Toolbox/FLEx Adjustments
nav_order: 10
permalink: /docs/05-toolboxflex-adjustments/a-divide-fields/
---
# 5A Divide fields
In Toolbox it is possible to have a reference field that points at more than one entry.  For instance:
```SFM
\cf saw, seen
```
However, for importing to FLEx, these need to be on separate lines:
```SFM
\cf saw
 
\cf seen
```

This applies for any reference field in FLEx (\cf, \sy, \an, \va, \mn, \re, \rn, etc.)
- You can use the script SplitRefs.pl to divide fields.
- That version is currently hard coded for most of the markers listed above, but it is expected that you will customize for the markers you need to split.
- There is another version called SplitRefs-re.pl that only splits \re and \rn.
