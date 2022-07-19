---
layout: default
title: 2 Analyze the database
has_children: true
nav_order: 20
---

## 2 Analyze the database

The second phase is analyzing the SFM database. There are 5 steps to this phase:

A. Preliminary text cleanup (unwrap lines, check line endings)

B. Assess Writing Systems [needs work]
 - Determine if encoding conversion is needed.
 - Helpful utility for assessing what characters exist in the data:  [UnicodeCCount.exe](https://scripts.sil.org/cms/scripts/page.php?site_id=nrsi&id=UnicodeCharacterCount)
 - Ensure linguist has a Unicode font and keyboard
 - Learn what sort orders are used
 - Be prepared to add these to the empty database

C. Enumerate the markers

D. Assess fixed fields
- Which fields have list content
- Is it consistent?
- Are custom lists or list items needed?

E. Inline formatting [needs work]
- Does it exist?
- Is it applied correctly?
- Should any be applied that isn't there?
