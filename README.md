
```
███╗   ███╗ █████╗ ██████╗  ██████╗ ██╗  ██╗
████╗ ████║██╔══██╗██╔══██╗██╔═══██╗╚██╗██╔╝
██╔████╔██║███████║██████╔╝██║   ██║ ╚███╔╝ 
██║╚██╔╝██║██╔══██║██╔══██╗██║   ██║ ██╔██╗ 
██║ ╚═╝ ██║██║  ██║██████╔╝╚██████╔╝██╔╝ ██╗
╚═╝     ╚═╝╚═╝  ╚═╝╚═════╝  ╚═════╝ ╚═╝  ╚═╝  Community.
```

# Betterlockscreen Theme Toolkit for Mabox Linux

This toolkit provides **user-friendly scripts** to generate, select, and apply custom Betterlockscreen themes on **Mabox Linux**.
It integrates with Mabox’s desktop wallpaper.

---

![BETTERLOCKSCREEN THEME GENERATION DEMO](demo/demo.mp4)

## Bash scripts involved

_(do not rename scripts - they depend on each other)_

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

![PASSWORD DEMO](demo/passwin.gif) 

![PASSWORDbox](demo/passwin-01.gif)

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
  betterlockscreen background regeneration

* Or use custom image path via yad

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
