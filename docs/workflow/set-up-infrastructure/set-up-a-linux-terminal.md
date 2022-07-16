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

### Finding Windows folders

### Navigating directories

### Redirection and Pipes in WSL
