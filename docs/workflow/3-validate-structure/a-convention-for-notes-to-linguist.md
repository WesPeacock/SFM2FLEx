---
layout: default
title: Convention for Notes to Linguist
parent: 3 Validate structure
grand_parent: Workflow
nav_order: 10
---
# Convention for Notes to Linguist
Below are some specific steps for validating the structure.  In the process, you may discover places where you need to "make a best guess" about what was intended in the data.  However, it is important for the linguist to be able to find and review these before he begins his lexicography work with the FLEx project you send them.  There needs to be a way to mark these places.

The recommendation is to create a new Standard Format Marker that you will add to the database, and then create a custom field in FLEx to import that marker to.  Then when you give the database to the linguist, include instructions about how to find these fields and what to do with them.  [Include sample document showing the kinds of instructions to give to a linguist with their completed import.]

You may need to make notes at different levels of the hierarchy.  Here is an example of some SFMs and FLEx custom field names that can be used for this purpose:
 - \ntImport
   - ImportNotes-Entry
 - \ntsImport
   - ImportNotes-Sense
 - \ntexImport
   - ImportNotes-Example

You may choose whatever names you like, for both the SFMs and the custom fields in FLEx.  The important things are to (a) do something, (b) make sure the contents of the field have enough information that the linguist will know which piece of data it is about, and (c) use different markers for different levels of the hierarchy.
