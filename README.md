[![Donate](https://img.shields.io/badge/Donate-PayPal-green.svg)](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=YYGKKE6FDX2KY)

![GPD Pocket Screen rotation utility](https://github.com/stockmind/gpd-pocket-screen-indicator/raw/master/screenshot.png)

# GPD Pocket screen rotation utility (Linux only)

With this utility and traybar indicator you can easily manage screen and touch rotation of your device.

This package will install daemons that will run on boot and will manage the screen rotation.

You can also switch from High DPI to Normal DPI mode to work easily on attached monitors with native DPI on Xorg.

I'm experimenting other features that may be added soon.

**This packages is not compatible with Ansible-playbook setup due to rotation scripts that may conflict. Clean your system before use this.
You may try this clean script at your own risk: [Clean Ansible Playbook script](https://github.com/stockmind/gpd-pocket-ubuntu-respin/blob/master/clean-ansible.sh)**

This is an indipendent module of another project: https://github.com/stockmind/gpd-pocket-ubuntu-respin

It can work without that setup but is *recommended* to run into an environment configured with those project files for a better user experience.

# Install

## Required dependencies

### Debian, Ubuntu, etc...:

 - python
 - python-gi
 - gksu
 - xinput
 - gir1.2-appindicator3-0.1

### Arch:

- gobject-introspection
- python2
- python2-gobject
- xinput
- gksu

## GNOME-Shell Users

Gnome users must install an extension for Gnome Shell (Choose one):

- https://extensions.gnome.org/extension/1031/topicons/
- https://extensions.gnome.org/extension/495/topicons/

This extensions will enable legacy tray icons on top bar.

## Install

Clone repository and run as root

    sudo ./install.sh

This will install gpdscreen rotation scripts, daemons and icons.
This will also remove old versions of my gpdtouch scripts.

Reboot after install is required.

# Uninstall

Clone repository and run as root

    sudo ./uninstall.sh

This will also remove old versions of my gpdtouch scripts. 

# Have an issue?

Check [Troubleshooting section.](#troubleshooting)
If your problem persist or is not on the list check [Problem reporting section](#problem-reporting) before open an issue.

# Troubleshooting

## No icon on GNOME Shell

[Check this](#gnome-shell-users)

## Touchscreen or display rotation is wrong after wake/sleep or screen lock

Sometimes it may happen that rotation of touch or display is wrong due to several factor, particularly on GNOME or derived Desktop Environments. You can fix this simply selecting with mouse the GPD Screen Rotation icon on the tray bar ( ![GPD Screen Rotation icon](https://github.com/stockmind/gpd-pocket-screen-indicator/raw/b26ef297ab46e1cb0c6534ff66571d60e10b25ad/icons/screen-rotation-button-black.png) ) and clicking on the desired rotation on menu.

Ex.
If your display is rotated in landscape correctly but touchscreen is not aligned, you can select "Rotate landscape" to fix this. The opposite is also valid.
The script will do it's best to compensate the alignment problems that may happen.

## Touchscreen stop to respond

You can try to use the "Reset touchscreen" option from the GPD Screen Rotation icon on your tray bar ( ![GPD Screen Rotation icon](https://github.com/stockmind/gpd-pocket-screen-indicator/raw/b26ef297ab46e1cb0c6534ff66571d60e10b25ad/icons/screen-rotation-button-black.png) ). It will ask for your password. Wait for 5 seconds then retry to use touchscreen. If problem persist try to put system in sleep for a bit or reboot your device.

## No GPD Screen Rotation icon shows at boot

In some system it may happen that tray icon won't show at boot. Try to run in a terminal

    gpdscreen-indicator
    
If it works add "gpdscreen-indicator" command to your system "Startup Application" utility to run it at boot.

Check also that your Desktop Environment is XDG-Compliant: https://wiki.archlinux.org/index.php/Desktop_entries#Autostart

# Problem reporting

To report a problem clone the repo, run "problem-reporting.sh" script and attach the output to your github issue. This will help debugging.

```
sudo ./problem-reporting.sh
```

# Credits

Base rotation script and daemons are based on initial bash work of chrisawcom 

Contributions by beeftornado, maxengel

Icons used: [Material Design by Google](https://www.flaticon.com/authors/google)

# Donate

If my work helped you consider a little donation to buy me a coffe... or an energy drink! :smile:

[![paypal](https://www.paypalobjects.com/en_US/i/btn/btn_donateCC_LG.gif)](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=YYGKKE6FDX2KY)
