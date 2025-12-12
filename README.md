# Betterlockscreen Theme Toolkit for **Mabox Linux**

This repository provides a set of tools designed **exclusively for Mabox Linux** to manage, generate, and select custom Betterlockscreen color themes.
The scripts integrate with Mabox’s desktop configuration logic, including its wallpaper handling and theming approach.

![ BETTERLOCKSCREEN THEME GENERATION DEMO ](https://gitlab.com/muzlabz/betterlockscreen-theme-creator/-/blob/main/demo/demo.webm?ref_type=heads)

The toolkit consists of:

* **betterlock-theme-generator**
  Interactive color-theme generator using YAD.
* **betterlock-themes**
  Theme picker / theme activator.
* **betterlock-menu**
  A unified launcher for generator, picker, and lockscreen actions.

These scripts are intended to be placed in:

```
~/bin/
```

Make sure `~/bin` is in your `PATH`.

---

## Features

### 1. Betterlockscreen Theme Generator

`betterlock-theme-generator` is an interactive GUI tool (YAD-based) that allows you to:

* Generate **Cyberpunk**, **Vibrant**, and **Pastel** color schemes
* Randomize and regenerate theme colors interactively
* Edit greeter text, verification text, warning text
* Adjust login-box background or make it fully transparent
* Choose font family
* Preview all theme color variables
* Save new themes directly into:

```
~/.config/betterlockscreen/themes/
```

Themes created by this generator can be immediately selected using **betterlock-themes**.

### 2. Betterlockscreen Theme Picker

`betterlock-themes`:

* Lists existing themes
* Allows activating a chosen theme
* Calls Betterlockscreen’s internal image generation
* Uses Mabox’s desktop background integration

### 3. Betterlock Menu

`betterlock-menu`:

* Provides a simple script or menu integration (e.g. rofi, jgmenu)
* Launches:

  * lockscreen
  * theme generator
  * theme selector

---

## Mabox Linux Integration

These tools rely on Mabox Linux’s custom wallpaper handling.
When the generator or theme selector updates a theme using the `-u` flag, **Mabox’s desktop image is used**, not a manually selected file.

**Important:**
Once a theme has been updated with `-u`, its generated images (with shadows) remain stored and used again if no new wallpaper is applied.

---

## About the `-u` Flag (Update Background Images)

Several Mabox utilities and the Betterlockscreen integration use `betterlockscreen -u` to:

* Regenerate lockscreen images
* Apply shadows
* Re-render blurred or dimmed variants
* Update transition layers for the animation

Behavior Notes

It takes a bit longer because background images and shadows must be processed.

During -u operations, the generator and the theme selector use Mabox’s current desktop wallpaper as the source image.

If -u is not used, Betterlockscreen simply reuses the previously generated background set.

This is expected behavior and not a bug.

**To change the lockscreen image, simply change your desktop wallpaper.**
**Mabox’s wallpaper handling automatically provides the new image to**
**Betterlockscreen when the theme is regenerated.**

---

## Scripts Included in This Toolkit

### **betterlock-theme-generator**

This script:

* Creates themed configuration files:
  `~/.config/betterlockscreen/themes/<theme-name>.theme`
* Uses:

  * YAD forms
  * Random color generation functions
  * Multi-language prompts (EN/PL/ES)
* Allows preview/regenerate/save loops
* Automatically launches theme selector when done:

  ```
  ~/bin/betterlock-themes
  ```

#### Internally it generates values for:

* login box / shadow
* font
* ring / inside / verification / wrong / separator colors
* foreground text colors (time, greeter, layout)
* editing greeter/verification/warning strings
* transparency toggles
* background color (fallback)

---

### **betterlock-themes**

This utility typically:

* Lists all theme files in `~/.config/betterlockscreen/themes/`
* Provides a GUI or menu to activate the selected theme
* Applies the theme and optionally:

  ```
  betterlockscreen -u <path>
  ```
* Follows Mabox’s desktop wallpaper logic

---

### **betterlock-menu**

Provides a menu-level interface.
Common actions:

* Lock
* Generate new theme
* Choose existing theme
* Regenerate background images (with `-u`)
* Open Betterlockscreen settings

This script simply acts as the orchestrator for the other two tools.

---

## Installation

Clone the repository:

```
git clone https://github.com/<your-repo>/betterlockscreen-mabox-themes.git
cd betterlockscreen-mabox-themes
```

Install scripts:

```
mkdir -p ~/bin
cp betterlock-theme-generator ~/bin/
cp betterlock-themes ~/bin/
cp betterlock-menu ~/bin/
chmod +x ~/bin/betterlock-*
```

Ensure `~/bin` is in your PATH:

```
echo 'export PATH="$HOME/bin:$PATH"' >> ~/.bashrc
source ~/.bashrc
```

---

## Usage

### Start theme generator:

```
betterlock-theme-generator
```

### Choose an existing theme:

```
betterlock-themes
```

### Open lockscreen menu:

```
betterlock-menu
```






