GNOME 
======
# prerequisites
Before doing anything, we need to install the essential GNOME packages. Therefore, install ```gnome-tweaks``` with the package manager of your distribution (here we are working on Arch Linux) so:
```
sudo pacman -S gnome-tweaks
```
Then you have to install ```extension-manager``` from aur so:
```
yay -S extension-manager
```
After this, update the system once ``` sudo pacman -Syu ```
# Plugins
then enter the [GNOME Shell Extensions](https://extensions.gnome.org/) website and install the following plugins:
### App Icons Taskbar
This allows you to see the running programs in the top panel.
### Blur my Shell
This allows you to make different parts of your Shell transparent or blur.
### Clipboard Indicator
Clipboard plugin. (not mandatory)
### Dash to Dock
Add bottom dock to your desktop.
### GSConnect
Similar to KDE Connect, but for GNOME, it provides the possibility of connecting the phone to the system.
### Iranian Persian Calender
Add Jalali calendar to the panel (optional)
### Logo Menu
Add a menu with your distru's logo (similar to the Windows Start button) in the upper left corner
### Quick Setting Tweaker
It provides the possibility of personalizing quick settings (upper right corner)
### RunCat
A small cat will be added to your top bar to slow down or speed up based on CPU usage
### Top Bar Organizer
It provides the possibility of moving and personalizing the items in the top bar

# 
1. To display the texts correctly, install one of the Nerd family fonts. [suggestion](https://github.com/ryanoasis/nerd-fonts/releases/download/v3.1.1/DroidSansMono.zip)
2. Then go to the [GNOME Look](https://www.gnome-look.org/) site and download the desired theme or icons.
3. Note:
+ After downloading and extracting the theme file, move its folder to this path ```~/.themes``` and the icons folder to the ```./icons``` so that they appear in ```gnome-tweaks```.
+ For my theme, I used the Dracula skin, which can be downloaded from this address. Icons can also be downloaded from this address. Extract the files and copy them to the mentioned folders. Then open gnome-tweaks. Open Appearance menu. Change the ```shell``` and ```legacy applications``` to ```Dracula``` and the icons to ```MacMojave-circle-black``` to apply the skins.
# Terminal
ddd

1. First ordered list item
2. Another item
⋅⋅* Unordered sub-list. 
1. Actual numbers don't matter, just that it's a number
⋅⋅1. Ordered sub-list
4. And another item.

⋅⋅⋅You can have properly indented paragraphs within list items. Notice the blank line above, and the leading spaces (at least one, but we'll use three here to also align the raw Markdown).

⋅⋅⋅To have a line break without a paragraph, you will need to use two trailing spaces.⋅⋅
⋅⋅⋅Note that this line is separate, but within the same paragraph.⋅⋅
⋅⋅⋅(This is contrary to the typical GFM line break behaviour, where trailing spaces are not required.)

* Unordered list can use asterisks
- Or minuses
+ Or pluses
