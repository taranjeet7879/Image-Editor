# Image Editor

A simple and interactive **browser-based Image Editor** built using **HTML, CSS, and JavaScript**.

The application allows users to upload an image, apply different image filters in real time, choose from multiple preset styles, reset the edits, and download the edited image as a PNG file.

## Features

* 🖼️ **Image Upload**

  * Upload an image directly from your device.
  * The image is displayed on an HTML Canvas.

* 🎨 **Real-Time Image Filters**

  * Brightness
  * Contrast
  * Saturation
  * Hue Rotation
  * Blur
  * Grayscale
  * Sepia
  * Opacity
  * Invert

* ✨ **Preset Filters**

  * Drama
  * Vintage
  * Old School
  * Cinematic
  * Vivid
  * Warm
  * Cool
  * Faded
  * Black & White
  * Sepia
  * Soft
  * Moody
  * Dreamy
  * Noir
  * Retro
  * Faded Film
  * High Contrast
  * Pastel
  * Dramatic Warm
  * Dusty
  * Matte
  * Arctic
  * Sunset

* 🔄 **Reset**

  * Restore all filters to their default values.

* 💾 **Download**

  * Download the edited image as a PNG file.

* ⚡ **Client-Side Processing**

  * Image editing happens directly in the browser.
  * No backend server is required.

## Technologies Used

* HTML5
* CSS3
* JavaScript
* HTML Canvas API
* CSS Canvas Filters

## Project Structure

```text
Image-Editor/
│
├── index.html
├── script.js
├── style.css
└── theme.css
```

### File Description

| File         | Description                                                       |
| ------------ | ----------------------------------------------------------------- |
| `index.html` | Contains the structure and user interface of the image editor     |
| `script.js`  | Handles image uploading, filters, presets, reset, and downloading |
| `style.css`  | Contains the main styling of the application                      |
| `theme.css`  | Contains additional theme and visual styling                      |

## How It Works

### 1. Upload an Image

The user selects an image using the file input.

JavaScript creates an image object and loads it onto an HTML Canvas.

```javascript
const img = new Image();
img.src = URL.createObjectURL(file);
```

### 2. Apply Filters

The application uses the Canvas 2D context's `filter` property to apply multiple effects.

For example:

```javascript
canvasCtx.filter = `
  brightness(...)
  contrast(...)
  saturate(...)
  hue-rotate(...)
  blur(...)
  grayscale(...)
  sepia(...)
  opacity(...)
  invert(...)
`;
```

The image is then redrawn on the canvas with the selected filters.

### 3. Adjust Filters

Each filter has a range slider.

For example:

```javascript
brightness
contrast
saturation
blur
grayscale
sepia
opacity
invert
```

When the slider changes, the filter value is updated and the image is immediately redrawn.

### 4. Use Presets

The application contains predefined filter combinations.

For example, the **Vintage** preset combines brightness, contrast, saturation, grayscale, and sepia values to create a vintage appearance.

Presets are generated dynamically from the JavaScript `presets` object.

### 5. Reset the Image

The Reset button restores all filter values to their default settings and recreates the filter controls.

### 6. Download the Edited Image

The edited canvas is converted into a PNG image using:

```javascript
imageCanvas.toDataURL();
```

The browser then downloads the result as:

```text
edited-image.png
```

## Running the Project

Because this is a frontend-only project, no backend or server installation is required.

### Option 1 — Open Directly

Open:

```text
index.html
```

in a modern web browser.

### Option 2 — Use VS Code Live Server

If you have the **Live Server** extension installed in VS Code:

1. Open the project in VS Code.
2. Open `index.html`.
3. Right-click the file.
4. Select **Open with Live Server**.
5. The application will open in your browser.

## Default Filter Values

| Filter       | Default |  Range |
| ------------ | ------: | -----: |
| Brightness   |    100% | 0–200% |
| Contrast     |    100% | 0–200% |
| Saturation   |    100% | 0–200% |
| Hue Rotation |      0° | 0–360° |
| Blur         |     0px | 0–20px |
| Grayscale    |      0% | 0–100% |
| Sepia        |      0% | 0–100% |
| Opacity      |    100% | 0–100% |
| Invert       |      0% | 0–100% |

## Preset System

The editor uses a JavaScript object to store preset configurations.

Each preset contains values for the available filters.

Example:

```javascript
vivid: {
  brightness: 105,
  contrast: 120,
  saturation: 175,
  hueRotation: 0,
  blur: 0,
  grayscale: 0,
  sepia: 0,
  opacity: 100,
  invert: 0
}
```

This makes it easy to add new presets in the future.

## Browser Compatibility

The project is designed for modern browsers that support:

* HTML5 Canvas
* JavaScript ES6+
* CSS filters
* File API
* `URL.createObjectURL()`

Recommended browsers:

* Google Chrome
* Microsoft Edge
* Mozilla Firefox
* Safari

## Important Notes

* Images are processed locally in the browser.
* No image is uploaded to a backend server.
* The project does not require an API key.
* The project does not require a database.
* The project does not require Python or Flask.
* Downloaded images are generated from the edited canvas.

## Future Improvements

Possible improvements for future versions include:

* Image cropping
* Image rotation
* Image flipping
* Resize controls
* Drawing tools
* Text on images
* Multiple image formats
* Undo/Redo functionality
* More advanced presets
* Before/after preview
* Drag-and-drop image upload
* Mobile-friendly editing controls
* Image quality/compression settings

## Learning Objectives

This project demonstrates practical use of:

* DOM manipulation
* JavaScript event listeners
* Objects and arrays
* Dynamic HTML element creation
* HTML Canvas
* Canvas image rendering
* CSS filters
* File handling in the browser
* JavaScript functions
* Dynamic UI generation

## License

This project is available for educational and personal use.

---

### Author

**Taranjeet**

Built as a frontend JavaScript project to practice browser-based image manipulation and interactive UI development.
