<!-- Links -->
[bmac]: https://www.buymeacoffee.com/adi1090x
[ko-fi]: https://ko-fi.com/adi1090x
[paypal]: https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=U3VK2SSVQWAPN
[patreon]: https://www.patreon.com/adi1090x

# Canvas

<p align="left">
  <img src="https://img.shields.io/badge/Maintained%3F-Yes-green?style=for-the-badge">
  <img src="https://img.shields.io/github/license/adi1090x/canvas?style=for-the-badge">
  <img src="https://img.shields.io/github/issues/adi1090x/canvas?color=violet&style=for-the-badge">
  <img src="https://img.shields.io/github/forks/adi1090x/canvas?color=teal&style=for-the-badge">
  <img src="https://img.shields.io/github/stars/adi1090x/canvas?style=for-the-badge">
</p>

A `bash` script to generate and apply different types of **gradient** & **blured** wallpapers.


## Changelog
+ Input Colors for wallpaper using `-c` option
+ Multi Color Support for `plasma` Wallpaper
+ Fedora Centerd Changes
    + Replaced `xcolor` with `gcolor3`
+

<img width="2559" height="1599" alt="main2" src="https://github.com/user-attachments/assets/7f154b03-99be-4c28-9ee4-e830f577414f" />


### Features

+ Generate a `solid color` wallpaper
+ Generate a `random blured` wallpaper
+ Generate linear, radial, bilinear(4 colored) & twisted `gradient` wallpapers
+ Generate random, twisted or colored `plasma` wallpapers
+ Allows you to pick colors or fetch colors from `.Xresources` file for wallpaper generation

### Dependencies

+ `imagemagick`
+ `feh`
+ ~`xcolor`~ `gcolor3`
+ `xrandr` (only if you use it on xfce)

### Installation

+ Clone this repository...
```bash
cd $HOME
git clone https://github.com/adi1090x/canvas.git
cd canvas
chmod +x canvas

# you can copy this script in bin dir for easy use
sudo cp canvas /usr/local/bin
```

+ Run the program and choose an option
```
$ ./canvas -h
┏━╸┏━┓┏┓╻╻ ╻┏━┓┏━┓
┃  ┣━┫┃┗┫┃┏┛┣━┫┗━┓
┗━╸╹ ╹╹ ╹┗┛ ╹ ╹┗━┛

Canvas V4.0 (Fedora Edition) - Wallpaper Generator
Developed By : Aditya Shakya (@adi1090x)

Usage: canvas [OPTIONS]

Options:
  -h, --help          Show this help message
  -S, --size WxH      Wallpaper size (default: 1920x1080)
  -s, --solid         Generate solid color wallpaper
  -l, --linear        Generate linear gradient wallpaper
  -r, --radial        Generate radial gradient wallpaper
  -t, --twisted       Generate twisted gradient wallpaper
  -b, --bilinear      Generate bilinear (4-point) gradient wallpaper
  -p, --plasma        Generate plasma wallpaper
  -B, --blurred       Generate random blurred wallpaper
  -n, --no-preview    Skip preview window
  -a, --autobg        Auto-set as wallpaper (implies -n)
  -R, --randomize     Generate random wallpaper
  -c, --colors COLORS Specify colors directly (see examples)

Examples:
  canvas -s -c "#FF5733"                    # Solid color
  canvas -l -c "#FF5733-#3498DB" -a         # Linear gradient, auto-set
  canvas -r -c "red-blue"                   # Radial with color names
  canvas -t -c "#E74C3C-#8E44AD"            # Twisted gradient
  canvas -b -c "#FF0000,#00FF00,#0000FF,#FFFF00"  # 4 colors for bilinear
  canvas -p -c "#FF6B6B-#4ECDC4"            # Plasma with colors
  canvas -R                                 # Random wallpaper
  canvas -S 2560x1440 -l -c "orange-purple" # Custom size


```

### Usage

Though you can pick colors, Here's a [list](https://imagemagick.org/www/script/color.php) of all supported color names.

### Common Issues

1. **Wallpaper not changing** : If your wallpaper is not changing, then open an issue and show me the output of `echo $DESKTOP_SESSION`.

2. **Not working on XFCE** : If this script is not working on xfce, then open the terminal and run `xfconf-query -c xfce4-desktop -m` and change the wallpaper (any) via *xfce4-settings-manager*. <br />
In terminal, *xfconf-query* will print lines starting with `set:`, which show which properties have been changed, check `screen` & `monitor` values and modify the script accordingly.
```bash
105   ## For XFCE
106   if [[ "$OSTYPE" == "linux"* ]]; then
107       SCREEN="0"
108       MONITOR="1"
109   fi

```

### FYI

+ In KDE, it changes the wallpaper in all the Activities.
+ If you can improve it, you're welcome.
+ Have Fun!
