<p align="center">
<img src="https://github.com/system76/pop-gtk-theme/raw/master/Pop_gtk-logo.png"/>
</p>

-------------------
## Pop-Purple
This is an easily customizable derivative of Pop-OS!s theme.
It themes both gtk and the popshell which is almost everything within the OS.

There was probably a way of doing this neatly, that is not what I did though.

### Customizing
Edit the `colors.scss` file to change the colors to be what you'd like.

Edit the  `meson.build` file and change the project name from `PopPurple` to whatever you'd like.

### Notes
To use the theme install [User Themes X](https://extensions.gnome.org/extension/3019/user-themes-x/) gnome shell 
extension. Configuring it within the extensions app should allow you to select the newly installed theme. 

COSMIC Dock doesn't like being themed and I do not know why this is. This can be fixed 
by just switching to [Dash to Dock](https://extensions.gnome.org/extension/307/dash-to-dock/) 
instead, which is what COSMIC Dock is based on, and additionally
it is just kind of better. Disable COSMIC Dock before installing Dash to Dock.

Pop's gtk theme usually is built as both a light and dark version. This theme is based off of the
dark version, and the light version has been stripped out almost entirely. there are still remnants
of this with some of the folder names, and additionally certain colors being set based on `$variant` 
being 'light'. For our case, `$variant` will always be 'dark'.

Also, remember to change the Active Hint Color in the pop shell menu. That isn't set by the system theme.

### ToDo
Some of the colors are embedded in svg files. These could be changed, either by
changing them to use an external css file with the wanted colors, or by replacing 
the colors directly. Either way, this hasn't been done yet, so for a few gtk 
elements, Pop's defualt blue and orange highlights can come through.

Pop Launcher selected items are hard to read. I don't know where the selected item text color is, but it needs
to be fixed.

-------------------

A GTK+ theme for Pop!_OS 


### Required Components
-------------------
Pop supports Gtk+ 3.22.x

 ```
 * Gtk+-3.0             >= 3.22
 * Gtk+-2.0             >= 2.24.30
 * gtk2-engines-pixbuf  >= 2.24.30
 * gtk2-engines-murrine >= 0.98.1
 ```

### Recommendations

- For GTK, use icons alongside [Pop Icon Theme](https://github.com/pop-os/icon-theme)
- For fonts, use:
 > Window Titles: Fira Sans SemiBold 10

 > Interface: Fira Sans Book 10

 > Documents: Roboto Slab Regular 11

 > Monospace: Fira Mono Regular 11


### Installation

Pop is intended to be installed through the package manager. Packages for Pop are available in PPA:
```
sudo add-apt-repository ppa:system76/pop
sudo apt update
sudo apt install pop-theme
```
It's recommended to use the `pop-theme` metapackage, as this will pull in all components of the look. However, individual components can be installed separately, e.g:
```
sudo apt install pop-gtk-theme
```
It's also recommended to restart the GNOME Shell after applying the theme of your choice.

Enter the Shell's command launcher
```
Alt + F2
```

This will restart the Shell after you hit Enter
```
r
```



### Installation from Git Source
----------------------------

This is the recommended method for users who aren't on Pop.

###### Note: You must have sassc installed in order to build Pop. Users of 17.04 or later can all build-dependencies using:

```
sudo apt install sassc meson libglib2.0-dev 
```

For making modifications to assets, you will additionally need these two:

```
sudo apt install inkscape optipng
```


1. If previous versions were installed/existed, remove them first.

 ```
 sudo apt remove pop-gtk-theme
 sudo rm -rf /usr/share/themes/Pop*
 rm -rf ~/.local/share/themes/Pop*
 rm -rf ~/.themes/Pop*
 ```

2. Clone the repository.

```
git clone https://github.com/pop-os/gtk-theme.git
cd gtk-theme
```

3. Generate the theme files.

```
meson build && cd build
ninja
```

4. Install the theme.

```
ninja install
```

#### Rebuilding after modifications:

You shouldn't need to rebuild the entire theme after modifications. If you make
changes to any GTK3 or GTK2 assets, delete the old rendered copies and use the
`render-assets.sh` script to regenerate those with new ones with your 
modifications. 

TODO
----
* Prepare for Steam theming (priority: Low)

Public License
--------------
 Most files: GPL-3.0+
 Upstream Adwaita: LGPLv2.1
 Sound theme: CC-BY-SA-4.0


 > **Note:**
 >
 > SVG files are licensed under CC BY-SA 4.0

Special Thanks to
--------------
 Nana-4, the developer of Materia.
 tista500 and the Adapta Theme Project: https://github.com/adapta-project/
