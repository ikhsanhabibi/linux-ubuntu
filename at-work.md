# Create debian package
https://www.iodigital.com/nl/history/intracto/creating-debianubuntu-deb-packages

## Required files under debian folder
There are a number of files in this directory that we should edit in order to customize the behavior of the package. The most important of them are control, changelog, copyright, and rules, which are required for all packages. 

# Debian control file
https://www.debian.org/doc/debian-policy/ch-controlfields.html#s-binarycontrolfiles

# Install debian package
dpkg -i packagename
sudo apt list --installed

# Remove devian package
dpkg --remove packagename

