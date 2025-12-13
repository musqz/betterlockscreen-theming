
```
███╗   ███╗ █████╗ ██████╗  ██████╗ ██╗  ██╗
████╗ ████║██╔══██╗██╔══██╗██╔═══██╗╚██╗██╔╝
██╔████╔██║███████║██████╔╝██║   ██║ ╚███╔╝ 
██║╚██╔╝██║██╔══██║██╔══██╗██║   ██║ ██╔██╗ 
██║ ╚═╝ ██║██║  ██║██████╔╝╚██████╔╝██╔╝ ██╗
╚═╝     ╚═╝╚═╝  ╚═╝╚═════╝  ╚═════╝ ╚═╝  ╚═╝  Community.
```

# Betterlockscreen Theme Toolkit for Mabox Linux (pl, es, en)

This toolkit provides **user-friendly scripts** to generate, select, and apply custom Betterlockscreen themes on **Mabox Linux**.
It integrates with Mabox’s desktop wallpaper.

---

![BETTERLOCKSCREEN THEME GENERATION DEMO](demo/demo.mp4)

## Bash scripts involved


1. **betterlock-theme-generator** – interactive color theme generator

2. **betterlock-themes** – select and activate existing themes

3. **betterlock-menu** – **main menu**

## Features

### 1. Theme Generator (`betterlock-theme-generator`)

* Choose a color style: **Cyberpunk**, **Vibrant**, or **Pastel**
* Randomly generate colors, with option to **regenerate until satisfied**
* Edit login, verification, and warning text
* Adjust login-box background or make it fully transparent
* Choose font family
* Preview all color variables
* Save themes directly to:

```
~/.config/betterlockscreen/themes/
```

Saved themes can then be selected using **betterlock-themes**.

### Login window demo's. 

_(fade effect is from picom)_


<img src="demo/passwin.gif" alt="loginbox" width="300"> <img src="demo/passwin-01.gif" alt="loginbox" width="300"> <img src="demo/passwin-02.gif" alt="loginbox" width="300">



---

### 2. Theme Picker (`betterlock-themes`)

* Lists all saved themes in `~/.config/betterlockscreen/themes/`
* Activate a chosen theme
* Optionally regenerates login box backgrounds, shadows, and transparency
* Integrates with Mabox wallpaper handling

---

### 3. Main Menu (`betterlock-menu`)

* Provides the main menu. a simple GUI interface (yad)
* Common actions:

![Main-menu](demo/menu.jpg)
  
---

## Save theme Quick or Slow ...

When applying or previewing themes:

* **Quick update (instant preview):**

  * Updates colors, fonts, and text immediately
  * Great for seeing changes without delay
  * Does **NOT** update login box background/transparency or shadows

* **Slow update (full regeneration):**

  * Updates colors, fonts, and text
  * Rengenerate mabox wallpaper as background
  * Regenerates login box shadows, and transparency

---

## Mabox Linux Integration

* Changing the desktop wallpaper updates the source image for 
  betterlockscreen background regeneration (Default)

* Or use `custom image` as background. Leave empty for Mabox default.

---

## Installation

1. Clone the repository:

```
git clone https://github.com/<your-repo>/betterlockscreen-mabox-themes.git
cd betterlockscreen-mabox-themes
```

2. Install the scripts:

```
chmod +x betterlock-*
cp betterlock-* ~/bin/
```

## Usage

### Main menu

```
betterlock-menu
```

## Note

* Themes are saved as `.theme` files in:

```
~/.config/betterlockscreen/themes/
```


## .Desktop template

```
[Desktop Entry]
Name=Betterlock Theme 
Comment=Choose betterlockscreen theme
Exec=/path/to/betterlock-menu
Icon=system-lock-screen
Terminal=false
Type=Application
Categories=Settings;Utility;
```

## Windows overview

<img src="demo/style.jpg" alt="style" width="300"> <img src="demo/generate.jpg" alt="generate" width="300"> 
<img src="demo/themes.jpg" alt="themes" width="300"> <img src="demo/background.jpg" alt="BG" width="300">
<img src="demo/help.jpg" alt="help" width="300">4

## Extra info yad title image Mabox way

Mabox has a LOGO SVG Conky `Mabox_logo_SVG_mbcolor.conkyrc` where one can choose between 3 variation with coloring options. 
The svg's are created automatic when using conky svg coloring edit menu _(preview)_
Path `$HOME/.icons/mabox-logo-*` is used to store the svg's.

	In the scripts at the top, look for...
	
```
ICON="$HOME/.icons/mabox-logo-3d.svg"

# all options
mabox-logo-3d.svg
mabox-logo-circle.svg
mabox-logo-square.svg
```

<img src="demo/mabox-logo.jpg" alt="loginbox" width="300">
