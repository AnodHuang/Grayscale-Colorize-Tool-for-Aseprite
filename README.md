# Grayscale Colorize Tool for Aseprite

A simple Aseprite extension that colorizes the **current cel** using a user-selected base color.

This tool is designed for grayscale sprites, shading layers, icons, and pixel art assets.  
It preserves transparency and remaps grayscale brightness into the chosen color.

---
## Keyboard Shortcut

After installing the extension, you may want to assign a keyboard shortcut for faster access.

### How to assign a shortcut

1. Open Aseprite
2. Go to **Edit > Keyboard Shortcuts**
3. Use the search box to find:

```text
Open Colorize Window
```

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
```
---
## Screen Shots
> Pop Window
<img width="1214" height="693" alt="image" src="https://github.com/user-attachments/assets/a6384b86-c9e4-4083-ba0b-86d9dfdc1122" />
> Colorized Image
<img width="1308" height="708" alt="image" src="https://github.com/user-attachments/assets/584292eb-4e1e-4dcd-9bd5-e2154296d2b6" />

