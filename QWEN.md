# WebAR-4A-Synergy Project

## Project Overview

WebAR-4A-Synergy is a Web-based Augmented Reality (WebAR) project that enables interactive AR experiences using marker detection. The project allows users to scan various markers (patterns and barcodes) using their device's camera to trigger 3D models, videos, and audio content.

The project was specifically designed for an "Anastasia's English School" WebAR-booklet, as mentioned in the index.html file. It uses JavaScript libraries including three.js for 3D rendering, jsartoolkit5 for AR marker detection, and custom threex extensions for AR functionality.

## Key Technologies and Libraries

- **three.js**: JavaScript 3D library used for rendering 3D models and scenes
- **jsartoolkit5**: AR toolkit for pattern and barcode marker detection
- **threex**: Custom extensions for AR functionality (THREEx.ArToolkitSource, THREEx.ArToolkitContext, etc.)
- **GLTFLoader/OBJLoader**: For loading 3D models in various formats
- **VideoTexture**: For embedding video content into the AR experience

## Project Structure

```
WebAR-4A-Synergy/
├── index.html              # Main entry point of the WebAR application
├── js/                     # JavaScript libraries
│   ├── three.js           # Core three.js library
│   ├── tween.umd.js       # Tweening library
│   └── various loaders    # Model and texture loading utilities
├── jsartoolkit5/          # AR toolkit library files
├── loaders/               # Model loader implementations
├── threex/                # AR extensions for three.js
├── textures/              # 3D model textures
├── cat-textures/          # Textures for cat model
├── data/                  # Data files including camera parameters
├── *.glb,*.gltf          # 3D models in GLB/GLTF formats
├── *.patt               # AR pattern marker files
├── *.mp4,*.mp3           # Video and audio content
└── *.png                 # Image files and barcodes
```

## Features

- Supports both pattern-based markers (.patt) and barcode markers
- Displays 3D models, videos, and images triggered by markers
- Plays synchronized audio content with AR experiences
- Handles 10 different markers simultaneously with different content types
- Responsive design that adapts to device cameras

## Content Configuration

The project is pre-configured with 10 marker slots, each associated with different types of content. These configurations are now stored in a separate `config.json` file, making the system more flexible and easily configurable without changing code.

The `config.json` file contains:

- **markers**: An array of marker configurations with properties:
  - `id`: Unique identifier for the marker
  - `type`: Either "pattern" or "barcode"
  - `patternName`: Name of the pattern file (.patt) when type is "pattern"
  - `barcode`: Numeric value when type is "barcode"
  - `contentType`: Either "model", "video", "image", or "controller"
  - `modelFile`: Path to 3D model file
  - `videoFile`: Path to video file
  - `audioFile`: Path to audio file
  - `scale`, `position`, `rotation`: Transformation properties for 3D objects
  - `repeatOption`: Whether to loop media content

- **settings**: Global configuration options:
  - `maxMarkers`: Maximum number of markers to process
  - `detectionMode`: AR detection mode
  - `cameraParametersUrl`: Path to camera calibration file
  - Other AR context parameters

This configuration-driven approach allows for easy modification of the AR experience without code changes.

## Building and Running

The project is designed to run as a static web application:

1. Simply open `index.html` in a modern web browser
2. The application will prompt for camera access on first run
3. Click on the screen to enter the WebAR experience
4. Point your camera at any of the supported markers to trigger the AR content

For optimal experience, the application should be run on a mobile device with a camera through a web browser that supports WebRTC.

## Development Notes

- The main logic is contained in the `<script>` tag within index.html
- Marker detection is handled by jsartoolkit5 with three.js integration
- The camera parameters file (`data/camera_para.dat`) is essential for proper AR tracking
- Model scaling, positioning, and rotation can be adjusted in the index.html file
- Audio and video content plays automatically when markers are detected

## Supported File Types

- 3D Models: `.gltf`, `.glb`, `.obj` (with `.mtl`)
- Images: `.png`, textures
- Videos: `.mp4`
- Audio: `.mp3`
- Marker Patterns: `.patt`
- Data: `.dat` (camera parameters)

## Known Components

- **Bender.glb**: 3D model of Bender character
- **cat.gltf**: 3D model of a cat (with textures in cat-textures/)
- **penguinex.glb**: 3D model of a penguin
- **model.glb**: Generic 3D model
- **Octopus_toy.glb**: 3D model of an octopus toy
- Various pattern files (.patt) for marker detection
- Multiple audio and video files for enhanced AR experience