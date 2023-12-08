## Create debian package
https://www.iodigital.com/nl/history/intracto/creating-debianubuntu-deb-packages

## Required files under debian folder
There are a number of files in this directory that we should edit in order to customize the behavior of the package. The most important of them are control, changelog, copyright, and rules, which are required for all packages.
https://www.debian.org/doc/manuals/maint-guide/dreq.en.html

## Debian control file
https://www.debian.org/doc/debian-policy/ch-controlfields.html#s-binarycontrolfiles

## Build debian package
dpkg-deb --build helloworld

## Install debian package
dpkg -i packagename
sudo apt list --installed | grep pakckage-name

## Remove devian package
dpkg --remove packagename

## chmod
![Screenshot from 2023-11-29 14-28-54](https://github.com/ikhsanhabibi/linux-ubuntu/assets/33756873/859f712c-995d-4136-b41e-22d8585c5370)
https://www.shellbefehle.de/befehle/chmod/

## BASH - Bourne-again shell
man bash
