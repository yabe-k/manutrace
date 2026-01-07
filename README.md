# ManuTrace
An HTML-based inferface for manually extracting movement trajectory data from a movie

A lightweight, browser-based tool for manually annotating and tracking object trajectories in images or videos.  
This application is designed for behavioral and ecological studies where automated tracking is difficult or unreliable, and precise manual correction or annotation is required.

The tool runs entirely in the browser, requires no installation, and supports intuitive mouse operations, keyboard shortcuts, and CSV-based data exchange.

---

## Features

- Load images or videos directly via drag & drop
- Manually add, move, and delete trajectory points
- Support for multiple object IDs
- Frame-by-frame navigation
- CSV export and import of trajectory data
- Undo / redo operations
- Offline-capable (single-file HTML application)

---

## Getting Started

### 1. Open the Application

* Use in online environment
  * Open https://yabe-k.github.io/manutrace/dist/ManuTrace.html

* Use in offline environment
  * Download the HTML file `dist/ManuTrace.html` from this repository and open it in a modern web browser (Chrome, Firefox, or Edge recommended).
No server or additional dependencies are required.

---

### 2. Load a Video or Image

- Drag and drop a video (`.mp4`, `.webm`, etc.) or image file onto the application window  
  **or**
- Use the file selection button in the toolbar

Once loaded, the media will be displayed in the main canvas.

---

### 3. Create Trajectories

1. Select an object ID
2. Click on the canvas to add a point at the current frame
3. Advance frames and continue adding points

Trajectory data are stored automatically in memory while the page is open.

---

## Mouse Operations

| Operation | Action |
|----------|--------|
| Left click | Add a trajectory point at the cursor position |
| Left click + drag | Move an existing point |
| Right click (or long press) | Delete a point |
| Mouse wheel | Zoom in / out (if enabled) |
| Drag canvas (background) | Pan the view (if enabled) |

---

## Keyboard Shortcuts

| Key | Function |
|----|---------|
| `Space` | Play / pause video |
| `←` / `→` | Move one frame backward / forward |
| `Shift + ←` / `Shift + →` | Move multiple frames |
| `Ctrl + Z` | Undo last operation |
| `Ctrl + Y` | Redo |
| `Delete` / `Backspace` | Delete selected point |
| `Number keys (1–9)` | Switch object ID |
| `Home` | Jump to first frame |

(Exact behavior may depend on browser and OS.)

---

## CSV Format

Trajectory data can be exported and imported as CSV files.

### Columns

Typical columns include:

- `id`
- `frame`
- `time_sec`
- `x`
- `y`
- `source`

Example:

```csv
id,frame,time_sec,x,y,source
1,0,0,0.512,0.438,manual
1,1,0.0333,0.519,0.442,interp
```
Coordinates are stored in normalized image coordinates unless otherwise specified.

## Data Safety
* If trajectory data exist and you attempt to leave the page, a confirmation dialog will appear
* Unsaved data will be lost if the page is closed without exporting

## Intended Use Cases
* Behavioral tracking of insects or other animals
* Manual correction of automated tracking results
* Educational demonstrations of movement analysis
* Small-scale or exploratory trajectory annotation tasks

## Limitations
* Manual annotation is time-consuming for large datasets
* Performance may degrade with very long videos or large numbers of objects
* Not intended as a replacement for high-throughput automated tracking systems

## Citation

If you use this software in academic work, please cite the following paper:

[To be filled]

Citation is not legally required by the license, but is greatly appreciated
and helps support further development.

