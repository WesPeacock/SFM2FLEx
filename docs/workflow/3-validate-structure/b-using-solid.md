---
layout: default
title: Using Solid
parent: 3 Validate structure
grand_parent: Workflow
nav_order: 20
---
# Using Solid
## General principles for using Solid
### Tips before beginning
 - Make sure your file is Unicode.
 - Your file can have either Unix or Windows line endings.  Solid will change it to Windows line endings every time you save it.  If you will be doing other operations after this that expect Unix line endings, you will need to change them before you do those operations.  Keep this in mind every time you open your file in Solid.
 - Before even opening the database in Solid, determine whether it places Part of Speech over Sense in the hierarchy, or below it.  This affects which template you choose the first time you open the database.  [TO DO--I am not sure *any* of the templates allow ps under sn.  Need to provide more guidance.]
 - Make sure the database uses \lx as the field marker.  If it doesn't, Solid will think it has no entries.  Change the database to use \lx if necessary.
### Video Tutorial
There is a video tutorial about getting working with Solid.

It covers getting started, a detailed explanation of the settings, and examples of using it to solve some common problems.  The notes below also cover general principles.  Not all of the principles explained below are demonstrated in the videos; working with both the videos and the notes below might give a fuller picture.  However, there is a lot about working with Solid that involves "developing an intuition" for how to do it effectively.  What is presented here is intended as a way to get started.

### General outline for working with Solid
All of the following are steps you'll need to do.  You may or may not do them in this order.  Sometimes it helps to start in this order, but along the way you may find something else you need to do first, and then come back to the step you started.  It is all kind of intuitive.  You'll develop your own intuitions about the best sequence as you work with more databases.
#### Opening the file the first time
 - Start Solid and use the "Open Lexicon" button to navigate to and open your SFM file.
 - You may be presented with a screen giving you a choice of encoding. One one side it may show what the data would look like if it interprets it as UTF8 Unicode, and on the other it will show CP-1252.  If you know that your file is Unicode, make sure the radio button for "utf-8" is chosen.
 - [TO DO: Add image here]
 - You will be presented with a choice of "templates".  Normally the default one ("MDF") is good enough to start with.
 - It will open your file and display it in Solid.  Sometimes there is a delay before it shows; be patient.  You will also see a message about any markers that were not in the template--don't worry, we will deal with these shortly.  Just click OK.
 - Once you open your file in Solid, it stores the "settings" for in a file with the same basename as your file, and with the extension .solid.  For instance, if you open a file called MyData.sfm in Solid, then the settings for it will be saved in MyData.solid.
 - In the future, you can probably just double click the .solid file to get your database open in Solid. (This will work if the extension .solid has been associated with the Solid program.)
 - Be sure to keep your data and the settings file in the same folder.
 - If you make a copy of your database and want to open the copy in Solid, then also make a copy of the .solid file and change the basename to match the basename of your copied file.  This will make it simpler to get it open and using the same settings, and it also preserves the settings you had before, in case for some reason you need to go back to them.
 - Solid makes it easy to make a copy of both your data file and the settings for it.  Under the File menu is a command "Save a Copy As..." that will copy both at the same time.  However, after the command, you will still be in the original version of the data file, not the copy.  If you intend to start working in the copy, then close Solid all the way, and open up the copy before beginning work again.

#### Assign every marker a parent
When you first open the file, any marker that is not a default MDF marker (or PLB, if you chose that template) will not have any settings configured.  All of these will not parse, and that will make it look like other fields don't parse, when in fact they do.  So the first step is to configure *some* settings for them.

 - Click on the red ??? to open the dialog for configuring a marker.  The minimum thing to do is to assign it a parent marker.  If you know where it fits in the hierarchy (e.g., entry level or sense level), go ahead and fill in the appropriate parent (e.g., lx or sn).  Look for the "Parent Markers" portion of the dialog, and the word "(New)".  Select that, and type the marker that this one comes under (without the backslash).
 - [TO DO: Add image here]
 - Assign *what seems to be true of this data*, even if it is not what you ultimately want for import.  The goal at this point is to get as many markers to parse as possible, discover the structure of the database, and discover things that need to be fixed.
 - If possible, choose "Once" for how many times it can occur.  In general, the more restrictive you are, the more you will learn about the structure of the file.  If you know for sure that it can occur more than once under its parent, choose "One or more times 'together'".  Only choose "One or more times" if you are certain that it may be interspersed with other markers (or after you have worked with the data enough to discover that).
 - There may be some that you truly don't know, and it is okay to leave some unassigned at this point, but try to assign as many as possible.

#### Start big
- It helps to get the highest level structure established first.
- Start by making sure the markers for Category (normally \ps) and Sense (normally \sn) are set up correctly.
  - If this database does not use \ps and \sn, then set up whatever markers it does use, in the way that \ps and \sn were set up.
  - Those defaults are:
    - \ps under \lx, occurs "more than once together", might be "required"
    - \sn under \ps, occurs "more than once together", probably not required
  - If this data has \sn over \ps, then the settings need to be adjusted to reflect that  [TO DO: Add details.]
- If you are not using \sn as the sense marker then verify that all the markers that should come under a Sense have the sense marker as their parent.  Scan through the list for the ones that have \sn as their parent, and change it to whatever you are using.  (For example, \de, \dn, \ge, \re)
- It is not uncommon for there to be some major problems.  However, fixing those will work better if there are not a bunch of little niggly parsing problems with other fields.  Once you have the "big picture" stuff in place, it may be best to delay fixing the major structural problems until you do a few other things.

#### Address the little stuff
Everything is intertwined in an analysis problem like this.  It is very common that one field that appears to be in error is not in fact wrong, but some other error is making this one look wrong.  Thus it is important to always have both the big and little picture in mind at the same time, if possible.

Clearing up some of the little problems early may help solve other problems by:
- Removing other error messages that are only there because something else was out of place.
- Reducing the number of error messages to only the ones about the "big stuff" that you are trying to solve.

Here are several things you can do; the order they are done in will vary depending on your data, and you will probably jump around from one to another, or revisit some of them several times.
- Look at the error messages for other fields (besides ps/sn/se).
- Start with the ones with the most occurrences.  Is there something obvious going on?  Can you fix something easily to make one big block or messages go away? [TO DO: add examples]
- Start with the ones with the fewest occurrences.  Sometimes these are easy to address.
- Pick one error message, and then step through a lot of the entries in that filter, and see if there is a general pattern for why those are failing.  If there is one thing you can do that will fix several of them, do that first.  Then come back and address the more diverse problems.
- Keep working until the only error messages left are the ones you put off working on "until the rest of the data is cleaner".

#### Some techniques
When you specify the structure in Solid, that does not get passed on to the FLEx import process, so you can do some "tricks" to help you validate the structure of the file.  Here are some examples.
- In general, try to make your settings as restrictive as possible, so you can discover more about the database:
  - If you start by saying something can occur "Once", then any time it occurs twice it will be flagged.  It may be an error, or it may mean you need to change the setting.  But you can quickly find all those occurrences and inspect them.
  - If you start by saying "One or more times together", then it will flag any time something else comes between these elements.  You can see if it is an error to fix, or a reality that needs to be reflected in the settings.
  - If you say that a marker "Must occur" under something else, you will find the places it wasn't included.  Maybe it is okay to omit it sometimes, but it is useful to see how many of those cases there are before you allow it.
  - It is more restrictive to "report error" than "infer [a marker]" when no parent is found.  You may want to start with "report error", and once you have learned enough, then switch to "infer [marker]".
- Just because MDF says that all examples should start with \rf, that doesn't mean \rf has to be there.  If your database does not have any \rf fields, then change \xv to have \sn as its parent, rather than an inferred \rf.
- When there is a pair of fields that usually occur together and in the same order, sometimes I will make the second one a child of the first, just so that if they ever do not occur as a pair or in that order, it will be flagged, and I can investigate whether there is some other problem.  Just because you tell Solid the second one is a child, that does not mean FLEx will interpret it that way, so this can be a useful trick.

  It can be especially helpful if you are not sure where in the hierarchy the cluster comes:  if you make the subsequent fields children of the first one, then you only need to change the first one if you are experimenting with where it goes in the hierarchy.

  Examples:
  - If you have normalized the \ps and have both \ps and \ps_orig, you can make the second one a child of the other, and you might even make the child be required ("Must occur") to discover if it was inadvertently omitted somewhere.
  - I usually make xe and xn children of xv.
  - If you have ge and gn, and they always occur in that order, you can make gn a child of ge (same for de/dn, re/rn, and any other fields with both WSs).

#### Go back to the big structural issues
Once you have cleaned up some of the "niggly details", then you can see more clearly what is happening with the structure of the senses and subentries.  Now is the time to try to get those in the right places.
- Senses:  A common problem with MDF files is that records without \sn in single-sense entries have all of their sense-level fields showing as an error (e.g., \ge, \de, \re).  This is because Solid only allows one parent per cluster of markers, whereas the FLEx import is able to infer it.
  - You could go ahead and let one or more of these markers "infer \sn" in case of an error.  Eventually you may do this.  But you may not start out with that.
  - If you want to learn anything about where the real \sn markers occur, do your investigating before you set up the "infer" rule.  Once you are satisfied that you understand how they are used (e.g., in relation to \ps or \se or other markers), then go ahead and set up the "infer" rule.
- If you are setting things up to infer \sn above sense-level markers, it will be most helpful if you only have to do it for one of them.  See if there is a certain marker that always occurs first, and see how far you get with setting up the infer rule for only that one.  (But if the marker that occurs first is allowed to occur more than once in the sense, that won't work.)
- If the database has subentries, determine if they ever occur between senses.  If so, you may have "subentries of senses", and this will be a more complicated import.  [TO DO: See section ??? for more info]
- Determine which fields inside a subentry need a different marker from the same fields at the entry level.  There are two reasons this might be needed:
  - There are some fields for which this matters for the FLEx import.  [TO DO: Describe how to tell, or point to a document that tells.]
  - If you will be promoting subentries out of senses, then that script needs to know how to tell it has found the end of the subentry.  If the marker that indicates you have left the subentry, is the same as a marker that can occur inside the subentry, then one or the other needs to be different.  (For instance, if you have \sn both in the mai entry and in the subentry, you may need to make all the ones inside the subentry into \snSE.  This has to be done by hand.)
- [TO DO:  Add some tips about how to tell.]
#### Additional operations
Other operations you may need to do with Solid
- Move some entry level fields up (out of the senses, up to the entry level)
- Delete empty fields.  (You have to enumerate all the ones you want to *keep*, so this can be a little tedious.)
- Experiment with different settings for some fields, so you can discover their behavior.  For instance,
  - Tell Solid that a field can occur only once; you will discover if it ever appears twice.
  - Say that a field is required.  You will find out if it is ever missing.
  - Make a sibling a child of the marker it seems to always occur after.  You will find out if they always occur in the same order.  (For instance, if you have both \ge and \gn, it is helpful to know if they always occur in the same order.  If you make \gn a child of \ge, you will find the places it comes before \ge.
- Markers/Data Shape Inventory: shows all possible sequences of markers that occur before or after a specified marker.  For instance, if you want to know if gn always follows ge, you could use this command and set the "radius" to "1".
- Markers/Data Value Inventory: shows all possible contents of one or more markers (useful for fields that might be list items)
