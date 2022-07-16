---
layout: default
title: 1C Download Perl scripts from GitHub
parent: 1A Set up infrastructure
grand_parent: Workflow
nav_order: 90
---
# 1C. Download Perl scripts from GitHub

The perl scripts and sample control files are saved on a site named github.com, in a space dedicated to the SIL Dictionary & Lexicography Services.  The link to the DLS section of GitHub is:

<https://github.com/sil-dictionary-lexical-services>

This page will explain how to download a Perl script from there.  Bookmark these instructions so you can refer to them when you encounter a place in these instructions that asks you to download a Perl script.

The pages on this site that ask you to use a certain script will normally provide a link to the page for that script on github.com. When you click on the link you will be taken to a page that looks something like the screenshot below.

### 1. Perl scripts or sample INI files

To download the file, Locate the button labeled Raw (green circle in the image below) at the top of the listing. Right-click on it with your mouse to get a menu that allows you save the file to your computer (red circle: "Save link as..."). If you left-click on it, you'll be dropped into a page where you can highlight the text and copy and paste it into an editor.

![A sample github page of a perl script](/assets/images/PerlScriptonGithub.png "The joinlines.pl script page on GitHub")

### 2. Documentation and other files in the repository

Files related to each other, or a specific project are joined together in a "repository" on GitHub. Github presents the repository structure as a web-wite.

You can browse the repository for documentation and other files by clicking on the link to the repository (either blue circle). You can click either in the path in the title of the file or in the title at the top of the page. If a folder has a README file, GitHub automatically displays it at the bottom of the folder page.

### 3. Additional modules

- Some of the scripts on this site assume that you have an additional module installed in your Perl system.  You only need to do that installation step once.  If you followed all the instructions for installing WSL, then you have already installed all the modules that will be needed for this site.
- When you follow the link for a script on the github site, the README for that script will tell you if it depends on having these modules installed.
- Any script that doesn't depend on these modules can be run as-is.
