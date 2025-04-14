# IriShift - Random Image Color Generator & Config Modifier

This Python project generates a color palette from a randomly selected image, extracts the most prominent colors, and uses them to update the configuration files for your system's appearance. Specifically, it modifies the background and foreground colors for the **Qtile** window manager and **Alacritty** terminal emulator.

## Features

- **Random Image Selection:** Selects a random image from a directory.
- **Color Palette Generation:** Uses the `colorthief` library to generate a color palette from the chosen image.
- **Color Intensity Calculation:** Determines the intensity of the colors for better contrast.
- **Background Darkening:** Darkens the first color to be used as the background color.
- **Configuration File Updates:** Updates `config.py` for **Qtile** and `alacritty.yml` for **Alacritty** to reflect the new colors.
- **Image Set as Wallpaper:** Automatically sets the chosen image as the system wallpaper using `nitrogen`.

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
2. Ensure you have the required dependencies installed:
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
python random_image_color_gen.py
```

## Customization
- Image Directory: Modify the path variable in the script to point to your desired image directory.
- Number of Colors: The script generates 15 colors by default, but you can change this in the colorGen() function.
- Color Processing: Modify the functions like colorIntensity() and backgroundDarker() if you'd like to change how colors are processed.

## Backup and Rollback
- Before modifying the configuration files, backups are created with the .bak extension. If something goes wrong, you can manually restore the original files from the backups.
