# Grayscale Colorize Tool for Aseprite

A simple Aseprite extension that colorizes the **current cel** using a user-selected base color.

This tool is designed for grayscale sprites, shading layers, icons, and pixel art assets.  
It preserves transparency and remaps grayscale brightness into the chosen color.

---

## Features

- Open a small dialog window inside Aseprite
- Pick a base color interactively
- Apply colorization to the **current cel**
- Preserve original alpha / transparency
- Works well for grayscale pixel art and shaded sprite parts

---

## How It Works

For each non-transparent pixel in the current cel:

- Read its grayscale brightness
- Multiply the selected base color by `gray / 255`
- Keep the original alpha unchanged

Equivalent logic:

```python
new_r = int(base_color[0] * (gray / 255))
new_g = int(base_color[1] * (gray / 255))
new_b = int(base_color[2] * (gray / 255))
