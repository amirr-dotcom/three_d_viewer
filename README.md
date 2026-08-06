# ThreeDViewer

A high-performance Flutter package for viewing 3D models (GLB/GLTF) with support for animations, camera controls, custom textures, and AR using Three.js and InAppWebView.

## Features

*   **GLB/GLTF Support**: Render high-quality 3D models seamlessly.
*   **Integrated AR**: Launch models in Augmented Reality (Scene Viewer on Android, Quick Look on iOS).
*   **Animation Control**: Play, pause, and scrub through specific animation layers.
*   **Interactive Hotspots**: Add clickable HTML-based hotspots that track points on the model.
*   **Auto-Rotate**: Customizable auto-rotation with controllable speed and direction.
*   **Intuitive Camera**: Supports orbit controls with customizable limits (up, down, left, right).
*   **Zoom Configuration**: Set initial zoom levels and define min/max zoom constraints.
*   **Auto-Centering**: Automatically center models at the origin for consistent viewing.
*   **Debug Helpers**: Toggle grid, axes, and target markers for development and positioning.
*   **Custom Loader**: Add your own Flutter widget as a loading indicator while the model loads.
*   **Background Transparency**: Support for transparent or custom-colored backgrounds.
*   **Local & Remote Assets**: Load models from Flutter assets or remote URLs.

## Getting started

Add `three_d_viewer` to your `pubspec.yaml`:

```yaml
dependencies:
  three_d_viewer: ^0.1.0
```

### Platform Setup

#### Android
Ensure your `minSdkVersion` is at least **21** in `android/app/build.gradle`.

#### iOS
Ensure your `Deployment Target` is at least **12.0**.
To use AR features, add the following to your `Info.plist`:
```xml
<key>LSApplicationQueriesSchemes</key>
<array>
  <string>https</string>
  <string>http</string>
</array>
```

## Usage

### Simple Implementation

```dart
import 'package:three_d_viewer/three_d_viewer.dart';

ThreeDViewer(
  assetPath: 'assets/models/my_model.glb', // or URL
  autoPlay: true,
)
```

### Advanced Implementation

```dart
final ThreeDViewerController _controller = ThreeDViewerController();

ThreeDViewer(
  controller: _controller,
  assetPath: 'assets/models/my_model.glb',
  backgroundColor: Colors.transparent,
  autoCenter: true,
  autoRotateConfig: ThreeDAutoRotateConfig(
    autoRotate: true,
    speed: 5.0,
  ),
  debugConfig: ThreeDDebugConfig(
    showGrid: true,
    showAxes: true,
  ),
  hotspots: [
    ThreeDHotspot(
      id: 'h1',
      position: [0, 1.5, 0],
      label: 'Head',
      color: Colors.red,
    ),
  ],
  onHotspotTapped: (id) => print("Tapped hotspot: $id"),
  onAnimationsLoaded: (animations) {
    print("Loaded ${animations.length} animations");
  },
)

// Control the viewer
_controller.toggleAnimation(true);
_controller.setMaterialColor('Body_Mesh', Colors.blue);
_controller.goToView(180, 90, 5.0); // Yaw, Pitch, Distance
_controller.launchAR();
```

## Additional information

For a full implementation example, check the `example` folder.

### Contributing
Contributions are welcome! Please feel free to submit a Pull Request.

### Issues
If you encounter any bugs or have feature requests, please file an issue on the GitHub repository.
