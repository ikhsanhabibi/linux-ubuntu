# linux-ubuntu

## Linux command

- Update kernel Linux : http://ubuntuhandbook.org/index.php/2020/02/ubuntu-18-04-4-released-kernel-5-3/

```
Paste : Ctrl + shift + V
Editor : Windows + E
Finder: windows + R
File manager: Windows + F
Make file xecutable: chmod +x filename.sh
```

## Installation
- IntelliJ : sudo snap install intellij-idea-community --classic OR sudo snap install intellij-idea-ultimate --classic
- DataGrip:  sudo snap install datagrip --classic
- Postgres 11: https://pgdash.io/blog/postgres-11-getting-started.html

- Git: https://www.liquidweb.com/kb/install-git-ubuntu-16-04-lts/
- GitHub: https://jdblischak.github.io/2014-09-18-chicago/novice/git/05-sshkeys.html#:~:text=Add%20your%20public%20key%20to%20GitHub&text=Select%20SSH%20Keys%20from%20the,your%20github%20password%20if%20prompted.

- DisplayLink: https://support.displaylink.com/knowledgebase/articles/684649-how-to-install-displaylink-software-on-legacy-ubun

- Unzip: sudo apt-get install unzip | unzip file.zip

 - NodeJS : https://www.digitalocean.com/community/tutorials/how-to-install-node-js-on-ubuntu-16-04
 
- Evolution


## Java on Linux Ubuntu

- Installer: https://oraclemirror.np.gy/jdk8/  OR https://oraclemirror.np.gy/jre8/
- How to install: https://www.youtube.com/watch?v=Zp10aJqj51M

- Script

```
And below there are commands from the film that i use:
/usr/lib/jvm/jdk1.8.0_231/bin:/usr/lib/jvm/jdk1.8.0_231/jre/bin
J2SDKDIR="/usr/lib/jvm/jdk1.8.0_231"
J2REDIR="/usr/lib/jvm/jdk1.8.0_231/jre"
JAVA_HOME="/usr/lib/jvm/jdk1.8.0_231"

sudo update-alternatives --install "/usr/bin/java" "java" "/usr/lib/jvm/jdk1.8.0_231/bin/java" 0
sudo update-alternatives --install "/usr/bin/javac" "javac" "/usr/lib/jvm/jdk1.8.0_231/bin/javac" 0
sudo update-alternatives --set java /usr/lib/jvm/jdk1.8.0_231/bin/java
sudo update-alternatives --set javac /usr/lib/jvm/jdk1.8.0_231/bin/javac

```

## Settings
- How to Adjust or Increase Mouse Scroll Wheel Speed in Linux : https://www.youtube.com/watch?v=UE_CVr_SOOE
- Get Night Shift Feature: https://askubuntu.com/questions/977221/how-do-i-enable-night-mode-in-display-of-xubuntu

```
Install redshift

sudo apt-get install redshift redshift-gtk

Edit GeoClue's config

sudo nano /etc/geoclue/geoclue.conf

Append the following lines to /etc/geoclue/geoclue.conf

[redshift]
allowed=true
system=false
users=

ctrl+o to save and ctrl+x to exit
 
Configure redshift

Example of a manual config, for Copenhagen, Denmark. See Redshift homepage for an additional config example.
Comment out or change the latitude and longitude for you location.
nano ~/.config/redshift.conf

[redshift]
temp-day=3500
temp-night=1700
location-provider=manual

[manual]
lat=55.7
lon=13.4
```

- Chrome: https://linuxize.com/post/how-to-install-google-chrome-web-browser-on-ubuntu-18-04/
```
wget https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb
sudo apt install ./google-chrome-stable_current_amd64.deb
```

- Spotify
```
snap install spotify
```


## IntelliJ
- Code blocks sorter: sort methods, variables, => right click then sort by alphabet : https://plugins.jetbrains.com/plugin/9450-code-blocks-sorter
- IntelliJ Keyboard Shortcuts : https://medium.com/better-programming/intellij-keyboard-shortcuts-to-swear-by-7638c0efcc76
```
Ctrl + E (Recent Files pop-up).

```

## Sony Vaio settings
- Brightness: https://askubuntu.com/questions/266601/sony-vaio-brightness-settings-not-changing

## WIFI Problem
- https://askubuntu.com/questions/769521/wifi-networks-are-not-showing-in-ubuntu-16-04

GIF file
- sudo apt install peek
- Windows: https://www.screentogif.com/

Pass
- sudo apt-get install keepass2

# Gitignore generator
- https://www.toptal.com/developers/gitignore

# Intsall Blender (AutoDesk look a alike)
- https://linuxconfig.org/how-to-install-blender-on-ubuntu-20-04-focal-fossa-linux-desktop


### VM
- Shared folder: https://www.youtube.com/watch?v=fmjwM2P2cjs
- How to Enable Copy and Paste in a VirtualBox Running Ubuntu Linux: https://www.youtube.com/watch?v=8MiPmL0YaJk

## Customization

- KeePass2 : ```sudo apt-get install keepass2```

- Opening start menu with the Windows key in Xubuntu: https://www.phpdeveloper.org.uk/opening-start-menu-with-the-windows-key-in-xubuntu/
```
- Open the Keyboard application (Start menu -> Keyboard).
- Switch to the Application Shortcuts tab.
- Click the Add button (Edit only allows you to change the command, not the shortcut).
- Enter xfce4-popup-whiskermenu as the command.
- When prompted, press the Windows key – it will usually show up as Super L.
```


## Dual boot
- How to Dual Boot Ubuntu 20.04 LTS and Windows 10: https://www.youtube.com/watch?v=Z-Hv9hOaKso
- How to Dual Boot Ubuntu 20.04 LTS and Windows 10 [ 2020 ] | UEFI - GPT Method: https://www.youtube.com/watch?v=aKKdiqVHNqw


# Hibernate
```
Just press Ctrl+Alt+T on your keyboard to open Terminal. When it opens, run the command(s) below:

sudo nano /var/lib/polkit-1/localauthority/10-vendor.d/com.ubuntu.desktop.pkla

Look for

[Disable hibernate by default in upower]
[Disable hibernate by default in logind]

Change the value of "ResultActive=no" to "ResultActive=yes" in both, 
press ctrl+x to exit the file. It will ask to save the change or not.
Press Y to save the change, if you're on Ubuntu restart your system.

```
