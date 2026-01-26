# Video Grid 0.3

**Video Grid 0.3** is a powerful, client-side web application that generates high-quality thumbnail contact sheets (grids) from video files. It runs entirely in your browser using HTML5, CSS3, and Vanilla JavaScript, requiring no server uploads and ensuring your video files remain private on your local machine.

## Features

- **Client-Side Processing**: All video processing happens locally in your browser. No data is uploaded to any server.
- **Automatic Metadata Detection**: Automatically detects video resolution, frame rate (FPS), codec, bitrate, and duration.
- **Smart Resolution Scaling**: Automatically suggests optimal output scales based on input resolution (e.g., 8K, 4K, 1080p) to balance quality and file size.
- **Customizable Grid Layout**: Choose any number of columns (2-12) and rows (2-13).
- **Frame-Level Editing**:
  - Click any thumbnail to fine-tune the exact timestamp.
  - Add custom text overlays to individual frames.
- **Extensive Styling Options**:
  - **Auto-Style Detection**: Analyzes video colors to recommend the best color palette (Light, Dark, Warm, Cool, etc.).
  - **50+ Color Presets**: categorized into Dark, Light, Warm, Cool, Nature, and Vibrant themes.
  - **Custom Typography**: Upload your own font files (.ttf, .otf, .woff) or choose from a wide list of web-safe fonts.
  - **UI Theming**: Switch the application interface between Ocean, Slate, Dark, Cyberpunk, Retro Terminal, and Light modes.
- **Flexible Export**:
  - Formats: WebP, JPEG, PNG.
  - Quality control (70% - 100%).
  - Options for timestamps, rounded corners, and grid gaps.

## Installation & Usage

### Installation

No installation is required. Video Grid 0.3 is a single, self-contained HTML file.

1.  Download the `index.html` file.
2.  Open the file in any modern web browser (Chrome, Firefox, Edge, Safari).

### Quick Start Guide

1.  **Load Video**: Click "Select Video" and choose a file from your computer.
2.  **Configure Grid**:
    *   Adjust the **Columns** and **Rows** selectors to set the grid size.
    *   The **Output Resolution Scale** is auto-selected based on your video's resolution (e.g., 12.5% for 1080p). You can manually change this using the chips.
3.  **Generate**: Click the **Generate** button. The app will capture frames from the video and display them in the grid.
4.  **Edit Frames (Optional)**:
    *   Hover over any thumbnail and click it to open the editor.
    *   Use the slider or manual input to change the timestamp.
    *   Enter custom text in the "Custom Text" field to add overlays (e.g., "Scene 1").
    *   Click "Update Thumbnail" to save changes.
5.  **Style Output**:
    *   Expand the "🎨 Output Image Style" section.
    *   Click on **Preset Chips** to change the color scheme instantly.
    *   Adjust colors manually using the color pickers.
    *   Select a font family or upload a custom font file.
    *   Toggle options like "Timestamps," "Rounded Corners," or "Grid Gap."
6.  **Export**:
    *   Select your desired **Export Format** (WebP recommended for quality/size balance).
    *   Set the **Quality**.
    *   Click **Download Image**.

## Output Styling

The application provides granular control over the final image's appearance:

- **Background & Text Colors**: Manually set the background, title, metadata, and timestamp colors.
- **Typography**:
    - **Font Family**: Choose from Sans-Serif, Serif, Monospace, Display, or System fonts.
    - **Custom Fonts**: Click "Upload Font File..." to use your own .ttf or .otf files.
    - **Title Weight**: Adjust the boldness of the main title.
- **Layout Options**:
    - **Grid Gap**: Adjust the spacing between thumbnails (None to Postcard).
    - **Rounded Corners**: Apply rounded corners to thumbnails and badges.
    - **Timestamps**: Toggle the visibility of timecodes on thumbnails.

## System Requirements

- **Browser**: A modern browser with support for HTML5 Video, Canvas API, and ES6+ JavaScript.
    - Recommended: Google Chrome, Microsoft Edge, Mozilla Firefox, Safari (latest versions).
- **Memory**: Processing large 4K or 8K videos requires a significant amount of RAM (8GB+ recommended for 4K).

## Known Limitations

- **Performance**: Generating grids for very long videos (hours) at high resolutions may be slow due to browser memory limits.
- **FPS Detection**: While the app attempts to detect the exact FPS using the `requestVideoFrameCallback` API, it may fall back to estimates (filename analysis or standard defaults) if the browser restricts access or the video format is unusual.
- **Video Codecs**: Browser support for decoding video depends on the underlying OS and browser installation (e.g., HEVC/H.265 support may vary on Windows vs. macOS).

## Technical Details

- **Version**: 0.3
- **Tech Stack**: HTML5, CSS3, Vanilla JavaScript (No frameworks).
- **Core Logic**:
    - Uses `HTMLVideoElement` to decode video frames.
    - Uses `HTMLCanvasElement` to capture, scale, and draw the final grid.
    - Uses `Blob` and `URL.createObjectURL` to handle file downloads.
