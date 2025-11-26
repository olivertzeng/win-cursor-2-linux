# 🖱️ Windows to Linux Cursor Converter

Convert Windows cursor themes to Linux format with ease! This tool automatically converts `.cur` and `.ani` files to Linux-compatible cursors using `cursorgen`.

## ✨ Features

- 🎯 **Smart Mapping**: Automatically maps Windows cursors to Linux equivalents
- 📁 **Proper Structure**: Creates standard Linux cursor theme directories
- 🎨 **Multiple Variants**: Generates all necessary cursor variants for complete compatibility

> **Note**: Originally implemented in Bash, then ported to Python for cross-platform compatibility and because Python was already required for cursorgen. The Bash version remains available but may be removed in future updates in favor of the Python implementation.

## 🚀 Quick Start

### Prerequisites

Install `cursorgen` from: https://github.com/meanvoid/cursorgen

### Usage

1. **Run the converter** (creates `input/` directory):
   ```bash
   ./convert_cursors.sh    # Bash version
   # or
   ./convert_cursors.py    # Python version
   ```

2. **Add your Windows cursors** to `input/theme-name/`:
   ```
   input/
   ├── My Cursor Theme/
   │   ├── Normal.ani
   │   ├── Help.ani
   │   ├── install.inf
   │   └── ...
   └── Other Cursor Theme/
       ├── Default.cur
       ├── Text.cur
       ├── install.inf
       └── ...
   ```

3. **Convert**:
   ```bash
   ./convert_cursors.sh
   ```

4. **Install** the converted theme:
   ```bash
   cp -r "output/My Cursor Theme" ~/.icons/
   ```

## 📂 Project Structure

```
cursor-converter/
├── convert_cursors.sh    # Bash implementation
├── convert_cursors.py    # Python implementation
├── input/               # Place Windows cursor themes here
│   └── theme-name/
│       ├── *.cur, *.ani
│       └── install.inf
└── output/              # Converted Linux themes
    └── theme-name/
        ├── index.theme
        └── cursors/
            ├── arrow
            ├── hand
            └── ...
```

## 🎯 Cursor Mappings

| Windows | Linux Variants |
|---------|---------------|
| **Default** | `arrow`, `default`, `left_ptr`, `top_left_arrow`, `size-*` |
| **Hand** | `draft`, `pencil` |
| **Link** | `grab`, `hand`, `hand1`, `hand2`, `openhand`, `pointer`, `pointing_hand` |
| **Text** | `ibeam`, `text`, `xterm` |
| **Busy** | `half-busy`, `wait`, `watch` |
| **Work** | `left_ptr_watch`, `pirate`, `progress` |
| **Cross** | `cross`, `crosshair` |
| **Move** | `all-scroll`, `closedhand`, `dnd-move`, `fleur`, `grabbing`, `move`, `size_all` |
| **Help** | `help`, `left_ptr_help`, `question_arrow`, `whats_this` |
| **Unavailable** | `circle`, `crossed_circle`, `dnd_no_drop`, `forbidden`, `no_drop`, `not_allowed` |
| **Horizontal** | `col-resize`, `e-resize`, `ew-resize`, `h_double_arrow`, `w-resize`, `size_hor` |
| **Vertical** | `n-resize`, `ns-resize`, `row-resize`, `s-resize`, `v_double_arrow`, `size_ver` |
| **Dgn1** | `nw-resize`, `nwse-resize`, `se-resize`, `size_fdiag` |
| **Dgn2** | `ne-resize`, `nesw-resize`, `sw-resize`, `size_bdiag` |
| **Alternate** | `bottom_*_corner`, `top_*_corner`, `*_side`, `*-arrow`, `up_arrow` |

### Custom Theme Installation
```bash
# User installation
cp -r "output/Theme Name" ~/.icons/

# System-wide installation
sudo cp -r "output/Theme Name" /usr/share/icons/
```
