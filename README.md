# RasterPixelInfo — QGIS Plugin

A QGIS plugin that displays **row index, column index, and pixel values** directly on the map canvas for every visible raster pixel as you zoom in. Includes a multi-layer comparison panel in a dockable side panel.

---

## Features

- **Canvas labels** — row and column index drawn on the top-left corner of every visible pixel
- **Pixel values** — band value(s) displayed in the center of each pixel
- **Pixel borders** — red outline drawn around every visible raster pixel, aligned to the actual raster grid
- **Dock panel** — shows row, column, all band values, pixel resolution, and map coordinates for the pixel under the mouse
- **Multi-layer comparison** — check any combination of raster layers to compare their values at the same geographic location simultaneously
- **CRS-aware** — works correctly when the raster CRS differs from the map canvas CRS
- **Independent toggles** — labels, values, and borders can each be turned on/off independently
- **Zoom threshold control** — set the minimum screen pixel size at which labels appear, to prevent clutter at low zoom

---

## Installation

### From QGIS Plugin Repository (recommended)

1. Open QGIS
2. Go to `Plugins → Manage and Install Plugins`
3. Search for **Raster Pixel Info**
4. Click **Install**

### From ZIP (manual)

1. Download the latest ZIP from the [Releases](https://github.com/khalilgh33/RasterPixelInfo/releases) page
2. In QGIS go to `Plugins → Manage and Install Plugins → Install from ZIP`
3. Select the downloaded ZIP and click **Install Plugin**

---

## How to Use

1. Load one or more raster layers in QGIS
2. Click the **Raster Pixel Info** button in the toolbar, or go to `Raster → Raster Pixel Info`
3. The dock panel opens on the right side
4. Select your primary raster layer from the dropdown
5. Move the mouse over the raster — the dock panel updates in real time
6. **Zoom in** until each pixel is large enough on screen (default threshold: 20 screen pixels per raster pixel)
7. Row/col labels, pixel values, and borders appear directly on the canvas

### Canvas Display

Each pixel shows two independent text elements:

```
┌─────────────────────┐
│r14 c27              │  ← row/col tag (yellow), top-left corner
│                     │
│       143.8         │  ← pixel value (cyan), centered
│                     │
└─────────────────────┘  ← red border
```

For multi-band rasters the value line shows all bands: `B1:143  B2:98  B3:61`

### Layer Comparison

In the **Layer Comparison** section of the dock panel:

- Check any raster layers you want to compare
- As you move the mouse, the table updates with row, column, and value(s) from every checked layer at the same geographic location
- The primary layer row is highlighted in blue
- Use **Check All** / **Clear All** buttons for convenience
- If the mouse is outside a layer's extent, the table shows `out of extent`

### Settings

| Setting | Description |
|---|---|
| Show row/col labels | Toggle the yellow r/c tag on canvas |
| Show pixel values | Toggle the cyan value label on canvas |
| Show pixel borders | Toggle the red pixel outline on canvas |
| Min zoom threshold | Minimum screen pixels per raster pixel before labels appear |

---

## Requirements

- QGIS 3.0 or later
- Python 3.6 or later (included with QGIS)
- No additional Python packages required

---

## Limitations

- Canvas labels appear only when zoom is sufficient (configurable, default: 20 screen pixels per raster pixel)
- Maximum 2000 pixels rendered simultaneously on canvas — zoom in further if this limit is reached
- Pixel value sampling speed depends on raster format and data provider; very large rasters with many bands may be slightly slower

---

## Screenshots

> *Add screenshots here after first use — drag images into this section on GitHub*

---

## Contributing

Bug reports and feature requests are welcome via the [Issues](https://github.com/khalilgh33/RasterPixelInfo/issues) page.

Pull requests are welcome. Please open an issue first to discuss what you would like to change.

---

## License

This plugin is released under the **GNU General Public License v2.0**, consistent with QGIS and its plugin ecosystem.

See [LICENSE](LICENSE) for full terms.

---

## Author

**Khalil** — Ph.D. researcher in GIS and Remote Sensing, Charles University, Prague

Plugin developed for practical use in land-use/land-cover change research and remote sensing workflows.

GitHub: [khalilgh33](https://github.com/khalilgh33)
