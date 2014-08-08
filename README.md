# CAPSLOCK TO F13
## BECAUSE CAPSLOCK IS NOT SO COOL

THIS IS A QUICK UDEV HWDB RULE TO REMAP CAPSLOCK TO F13,
BECAUSE HITTING CAPSLOCK ACCIDENTALLY CAN BE QUITE AWFUL.
IT GIVES YOU A BRAND NEW KEY TO MAP TO, INSTEAD OF YET
ANOTHER CONTROL KEY.

### INSTALLATION

IF YOU ARE USING ARCH LINUX JUST USE THE `PKGBUILD` FILE WITH
`makepkg` AND INSTALL THE RESULTING PACKAGE.

```
makepkg
pacman -U capslock-to-f13-0.0.1-1-any.pkg.tar.xz
systemctl restart udev
```

IF YOU ARE NOT USING ARCH LINUX OR WANT TO INSTALL THIS MANUALLY,
IT'S PRETTY EASY.

* COPY THE HWDB FILE TO `/etc/udev/hwdb.d/90-capslock-to-f13.hwdb`
* RUN THE UDEV HWDB UPDATE COMMAND `udevadm hwdb --update`
* RESTART UDEV

### GNOME 3.12

ALSO I HAD SOME PROBLEMS WITH THE BINDING IN GNOME 3.12, EVEN
THOUGH IT USED TO WORK.  TO RESOLVE THIS I ADDED AN XMODMAP FILE
WITH THE FOLLOWING, TO STOP IT FROM BINDING AS XF86TOOLS.

```
keycode 191 = F13 F13 F13
```

AND THEN BECAUSE GNOME DEVELOPERS ARE EVEN MORE INSANE I HAD TO
DISABLE THEIR KEYBOARD SETTINGS PLUGIN.

```
$ gsettings set org.gnome.settings-daemon.plugins.keyboard active false 
```
