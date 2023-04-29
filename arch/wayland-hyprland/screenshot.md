# Take Screenshots

1. grim for capturing the entire screen and save it to file
2. slurp to select an area of the screen
3. wl-clipboard to pipe this area to the clipboard

Install via pacman.

```
sudo pacman -S grim slurp wl-clipboard
```

1. Capture entire screen and save it to a file. Base dir is home folder.

```
grim screenshot
```

2. Open window to manually select the area of the screenshot and save it to file.

```
grim -g "$(slurp)" screenshot.png
```

3. Open window to manually select the area of the screenshot and save it to clipboard.

```
grim -g "$(slurp)" - | wl-copy
```

## Automatic usage with wayland compositors

If you want to use this with something like Hyprland you can edit the `.config/hypr/hyprland.conf` and paste the following to manually select a area of the screen and save the screenshot to the clipboard when pressing the Super key and `S`.

```
# .config/hypr/hyprland.conf
bind = $mainMod, S, exec, grim -g "$(slurp)" - | wl-copy
```


