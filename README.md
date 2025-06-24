# IriShift - Random Image Color Generator & Config Modifier

This script looks for dominant colors from a randomly selected image and uses that to theme your *Qtile* and *Alacritty* setup.

## Features

- Theme color generation from a randomly selected wall in a given directory
- Auto-updates the config files: The `config.py` for Qtile and `alacritty.yml` for Alacritty.
- The randomly selected image is also updated as the wallpaper using `nitrogen`

## Requirements

- Python 3.x
- `colorthief` library (`pip install colorthief`)
- `nitrogen` (for setting the wallpaper)
- A system using **Qtile** as the window manager and **Alacritty** as the terminal emulator

## File Structure

- **Main Script:** The Python script that performs all the operations.
- **/home/Dew/.github/walls/.walls/**: Directory containing images for wallpaper.
- **/home/Dew/.config/qtile/config.py**: Configuration file for Qtile, updated with the new color scheme.
- **/home/Dew/.config/alacritty/alacritty.yml**: Configuration file for Alacritty, updated with the new background color.

## Installation

1. Clone this repository to your local machine.
2. Ensure you have `colortheif` installed:
   ```bash
   pip install colorthief
   ```
3. Ensure you have Qtile and Alacritty configured on your system.

## How It Works

1. The script selects a random image from the specified directory.
2. It generates a color palette from the image using the `ColorThief` library.
3. The script calculates the intensity of the colors and chooses a background color based on brightness.
4. It updates the configuration files for **Qtile** and **Alacritty** to use the new color scheme:
   - `bgColors` and `fgColors` for **Qtile** are updated.
   - The `background` color in **Alacritty** is updated.
5. The script sets the chosen image as the wallpaper using the `nitrogen` tool.
6. A backup of the original configuration files is created (with the `.bak` extension).

## Usage

1. Run the script, and it will automatically:
   - Pick a random image.
   - Generate the color palette.
   - Update configuration files for **Qtile** and **Alacritty**.
   - Set the chosen image as the wallpaper.

```bash
python irisShift.py
```

## Backup and Rollbacks
Before modifying the configuration files, backups are created with the .bak extension. If something goes wrong, you can manually restore the original files from the backups.
