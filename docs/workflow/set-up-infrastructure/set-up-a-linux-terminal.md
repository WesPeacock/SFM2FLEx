---
layout: default
title: Set up a Linux terminal
parent: Set up infrastructure
grand_parent: Workflow
nav_order: 80
---
# Set up a Linux terminal

Many of the instructions on this site assume you have a Linux terminal.  Windows Subsystem for Linux (WSL) is one way to get that on a Windows machine.  The preferred Linux system is Ubuntu. The purpose for setting up a Linux terminal is that DLS has created some Perl scripts to do things (like add, delete, rename or rearrange fields, etc.) to the SFM files in order to make the file easier to import correctly into FLEx. These scripts can only be run in a Linux terminal.

This page tells you how to install WSL on a Windows machine and gives a brief introduction of some of the salient differences between Linux and Windows terminals.

## Installing WSL

### Preparing Windows 10
If you are running Windows 10, you may need to update your Windows Settings to allow WSL.  For Windows 11, this is no longer needed
    - <https://docs.microsoft.com/en-us/windows/wsl/install-win10>

### Determining which version of Ubuntu to install
SIL has produced some utilities for Ubuntu that may not be available in the most recent version of Ubuntu. As of July 2022, the most recent SIL enhanced version of Ubuntu was 20.04.

You can check for newer versions at the Wasta-Linux downloads site (<https://wastalinux.org/home/download/>). Don't use the Wasta-Linux download, but the Ubuntu version that matches the current Wasta-Linux version will have the SIL enhancemants.

### Downloading WSL from the Microsoft Store
Go to the Microsoft store and select the version of Ubuntu you want. Follow the installation instructions there.

 - Note that you have to reboot after installing WSL.
 - When you first run it, it will ask you to create a username and password.  Be sure to write this down where you can find it in the future, as you will need it for the following steps, and you may need it sometime far into the future when you may have forgotten that you even created a password.
 - After you have installed WSL and have it running, you will want to tell it to update any software packages that were installed with it.  To do that, run the following command within
the WSL terminal window:
```bash
sudo apt update && sudo apt upgrade
```
 - It will ask you for a password.  Provide the password you created when you installed WSL

## Adding some necessary Perl modules & other utilities

Run the following commands within the terminal window.  [Note:  if you select a string of text and copy it (for instance, using Ctrl-C on the commands on this site), then you can paste that string into the WSL terminal by right-clicking at the prompt.]
```bash
echo "export PERL_UNICODE=SDA" >> ~/.bashrc
echo 'export PERL5OPT="-Mutf8 -MEnglish"' >> ~/.bashrc
sudo apt install build-essential libxml-libxml-perl dos2unix zip unzip
```
The system should install a large number of packages. If it asks for permission, reply "yes"
```bash
sudo cpan install Config::Tiny
```
Optionally install  Consistent Changes and the TECkit Unicode converter in the SIL packages repository:
```bash
(wget -O- https://packages.sil.org/keys/pso-keyring-2016.gpg | sudo tee /etc/apt/trusted.gpg.d/pso-keyring-2016.gpg)&>/dev/null
(. /etc/os-release && sudo tee /etc/apt/sources.list.d/packages-sil-org.list>/dev/null <<< "deb http://packages.sil.org/$ID $VERSION_CODENAME main")
sudo apt update
sudo apt install silcc teckit
```

## Using WSL
It is beyond the scope of this material to explain how to use WSL, but the most important things you need to know are:
- How to start it and get a terminal window
- How to find a Windows folder/directory from the terminal
- How to change directories within your Windows directory structure
- How to run Perl

### Finding Windows folders in WSL
- Linux documentation refers to Windows folders as "directories".

- The way to change directory in Linux is with the command "cd" and the path you want to get to.

- If you are typing a command and somehow get stuck (for instance, you have typed something where it is waiting for you to input something, but you don't know what, or you didn't mean to type that), you can get out of the command by typing Ctrl-D or Ctrl-C.  One or the other of those should get you back to the command prompt so you can start a new command.

- Windows and Linux specify directories differently
- Case is significant in Linux filenames and commands
- name in quotes vs using \<space>
- Some examples:
  - If you have a file named "Notes to Myself.txt" in a sub-directory "Stuff"
  - Windows can specify the file as:
    - ".\Stuff\Notes to Myself.txt" or ".\STUFF\NOTES TO MYSELF.TXT"
  - Linux uses:
    - ./Stuff/Notes\ to\ Myself.txt
- In WSL, to get to any of the folders on your Windows system, you have to start by specifying a path that starts with "/mnt/c/Users"  (This is called an absolute path, because it references the full path, starting from the root.  An absolute path references the same folder, no matter which folder you are in when you use it.)
- For instance, to get to your Documents folder, you would give the command:
```bash
cd /mnt/c/Users/<MyUserName>/Documents
```
- The command prompt in the terminal shows you the path of the folder you are currently in.

- Once you are in any Windows folder, you can use relative paths with the cd command (see below).

### Navigating directories

### Redirection and Pipes in WSL
