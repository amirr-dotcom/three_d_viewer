# ThreeDViewer

A high-performance Flutter package for viewing 3D models (GLB/GLTF) with support for animations, camera controls, and custom textures using Three.js and InAppWebView.

## Features

*   **GLB/GLTF Support**: Render high-quality 3D models seamlessly.
*   **Animation Control**: Play, pause, and scrub through specific animation layers.
*   **Intuitive Camera**: Supports orbit controls with customizable limits (vertical/horizontal angles).
*   **Zoom Configuration**: Set initial zoom levels and define min/max zoom constraints.
*   **Auto-Centering**: Automatically center models at the origin for consistent viewing.
*   **Debug Helpers**: Toggle axes and grid helpers for development and positioning.
*   **Custom Loader**: Add your own Flutter widget as a loading indicator while the model loads.
*   **Background Transparency**: Support for transparent or custom-colored backgrounds.
*   **Local & Remote Assets**: Load models from Flutter assets or remote URLs.

## Getting started

Add `three_d_viewer` to your `pubspec.yaml`:

```yaml
dependencies:
  three_d_viewer: ^0.0.2
```

### Platform Setup

#### Android
Ensure your `minSdkVersion` is at least **21** in `android/app/build.gradle`.

#### iOS
Ensure your `Deployment Target` is at least **12.0**.

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
  showDebugHelpers: false,
  zoomConfig: ThreeDZoomConfig(
    initialZoom: 1.0,
    minZoom: 0.5,
    maxZoom: 2.0,
  ),
  initialTargetPosition: [0, 1.0, 0], // Look at y=1.0
  onAnimationsLoaded: (animations) {
    print("Loaded ${animations.length} animations");
  },
)

// Control animations
_controller.toggleAnimation(true);
_controller.setAnimationProgress('Walk', 0.5);
```

## Additional information

For a full implementation example, check the `example` folder.

### Contributing
Contributions are welcome! Please feel free to submit a Pull Request.

### Issues
If you encounter any bugs or have feature requests, please file an issue on the GitHub repository.
