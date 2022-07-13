---
layout: default
title: PLB Imports
nav_order: 40
has_children: true
permalink: /docs/PLBImports
---

# PLB Imports
{: .no_toc }

Dictionaries from the Philippines Branch (PLB) follow a different standard than most Toolbox dictionaries that are imported.  Some special considerations in PLB dictionaries include:
 - Special markers for words borrowed from other languages
 - More lexical relations beyond "synonym" and "antonym"
 - Subentries specified for different "Complex Form Types" (derivations, compounds, idioms, sayings)
 - Factors related to the Philippine voice system
   - specific markers (\oi, \og, \oa) without built-in fields in FLEx
   - challenges with how to word translations of example sentences
   - inflection/derivation continuum
 - Roots with fluid lexical categories, depending which affixes are attached
 - Subentries of senses
 - Exemplars in senses
 - Markers that occur at both entry and sense level
 - Empty markers that have a meaning just by their presence or absence

There are approaches to handling all of these phenomena when importing a dictionary into FLEx.
