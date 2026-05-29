# ManuTrace

An HTML-based interface for manually extracting movement trajectory data from a movie.

A lightweight, browser-based tool for manually annotating and tracking object trajectories in images or videos.  
This application is designed for behavioral and ecological studies where automated tracking is difficult or unreliable, and precise manual correction or annotation is required.

The tool runs entirely in the browser, requires no installation, and supports intuitive mouse operations, touch/pen gestures, keyboard shortcuts, and CSV-based data exchange.

---

## Features

- **Collapsible Sidebar Sections**: Clean, accordion-style side panel sections (Video settings, Display settings, Operation mode, Tracking data, Shortcut keys) to optimize screen space.
- **Dynamic ID Switcher & Creator**: 
  - Click anywhere on the editing ID badge (color dot and text) to instantly open a dropdown list of currently existing IDs.
  - Circular `+` button to automatically create and switch to the smallest available positive integer ID (`1`, `2`, ...).
- **Multi-device Input Modes**: Choose between dedicated Mouse, Touch Panel, and Pen modes to unlock intuitive gestures (pinch-zoom, multi-finger pan) optimized for your device.
- **Timeline Drawer Operations**: Real-time visualization of tracking status with professional tools to split, merge, rename, or delete tracking lines.
- **Auto Seek after Click**: Speeds up annotation by automatically advancing the video after plotting a point.
- **Load Media via Drag & Drop**: Load video files (`.mp4`, `.webm`, etc.) by dragging them directly onto the canvas.
- **CSV Data Exchange**: Export annotations or import/restore previous tracking data easily.
- **Undo System**: Supports undoing point additions, merges, splits, deletions, and renames (`Ctrl+Z`).
- **Offline-capable**: A single-file HTML application requiring no installation or internet connection.

---

## Getting Started

### 1. Open the Application

* **Online**: Open https://yabe-k.github.io/manutrace/dist/ManuTrace.html in a web browser.
* **Offline**: Download the `dist/ManuTrace.html` file and double-click to open it in any modern browser (Chrome, Firefox, or Edge recommended).

---

### 2. Load a Video

- Drag and drop your video file anywhere onto the application window  
  **or**
- Click **"Select a file"** in the sidebar.

---

### 3. Choose your Operation Mode

Choose the mode in the **Operation mode** sidebar section according to your device:

#### 🖱️ Mouse Mode
- **Left click**: Add a tracking point at the cursor position.
- **Left click + drag**: Move an existing manually entered point.
- **Right click + drag**: Pan the canvas.
- **Right click (single click)**: Delete the manually entered point at the current frame.
- **Mouse wheel**: Zoom in / out at the cursor position.

#### 📱 Touch Panel Mode
- **Tap**: Add a tracking point at the tapped position.
- **2-finger pinch**: Zoom in / out.
- **2-finger drag**: Pan the canvas.

#### 🖊️ Pen Mode
- **Pen tip tap**: Add a tracking point.
- **Pen tip drag**: Move an existing manually entered point.
- **1-finger drag**: Pan the canvas.
- **2-finger pinch / drag**: Zoom & Pan.
- **1-finger tap**: Play / pause video.

---

## Keyboard Shortcuts

| Shortcut | Action |
|:---|:---|
| `Space` | Play / Pause video |
| `←` / `→` | Jump backward / forward by default step (e.g. 0.2s, customizable) |
| `Shift` + `←`/`→` | Jump by intermediate step (e.g. 1.0s, customizable) |
| `Ctrl` + `←`/`→` | Jump by large step (e.g. 3.0s, customizable) |
| `Ctrl` + `Shift` + `←`/`→` | Jump by extra large step (e.g. 10.0s, customizable) |
| `Ctrl` + `Z` | Undo the last action (add, delete, split, merge, rename) |
| `Ctrl` + `S` | Save CSV |
| `Ctrl` + `Mouse Wheel` | Seek frame-by-frame |
| `Shift` + `Mouse Wheel` | Increase / decrease playback speed |
| `Backspace` / `Delete` | Delete the manually entered point at the current frame |
| `Alphanumeric (0-9, a-z)` | Switch active editing ID |

---

## Timeline Operations

Double-click the timeline bar or click the title to expand it. The drawer lets you visually audit your tracks:
- **Scissors (Split)**: Split the selected track into two separate tracks at the current frame.
- **Code Merge (Merge)**: Merge two tracks by entering their IDs. Points in overlap regions will be selectively kept.
- **Pen (Rename)**: Rename the active ID to a new string.
- **Trash (Delete)**: Permanently delete the selected track.

---

## CSV Format

Trajectory data are exported as standard CSV using the original video's absolute pixel coordinates.

### Columns

- `id`: Track/object identifier.
- `frame`: 0-indexed frame number.
- `time_sec`: Time in seconds.
- `x`: X-coordinate, in absolute pixels of the original video.
- `y`: Y-coordinate, in absolute pixels of the original video.
- `source`: Tracking source (`manual` for manually plotted points, `interp` for spline-interpolated points).

Example:
```csv
id,frame,time_sec,x,y,source
1,0,0.000000,512.000,438.000,manual
1,1,0.033333,519.000,442.000,interp
```

---

## Data Safety

- If unsaved tracking data exist, the browser will display a confirmation prompt if you attempt to reload or close the tab.
- Always remember to export your work by clicking **Export CSV** (or `Ctrl + S`) before closing the application.

---

## Citation

If you use this software in academic work, please cite the following paper:

*[To be filled]*

---

## License

This project is licensed under the MIT License.
