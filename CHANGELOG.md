## 0.1.1

* **Web Support**: Added initial support for Flutter Web.
* **iOS Stability**: Improved tap detection and OrbitControls stability on iOS.
* **JS Fixes**: Added `resetPointers` to prevent "stuck" interactions during animations or double-taps.
* **Bug Fixes**: Adjusted tap sensitivity threshold for better responsiveness.

## 0.1.0

* **AR Support**: Added `launchAR()` method to view models in Augmented Reality on iOS and Android.
* **Hotspots**: Introduced `ThreeDHotspot` for interactive, tracking markers on 3D models with click callbacks.
* **Auto-Rotate**: Added `ThreeDAutoRotateConfig` to control model rotation automatically.
* **Dynamic Material Control**: Added `setMaterialColor()` to change mesh colors at runtime.
* **View Navigation**: Added `goToView()` to animate the camera to specific angles and distances.
* **Advanced Debugging**: Replaced `showDebugHelpers` with a more granular `ThreeDDebugConfig`.
* **Improved Interaction**: Added `onObjectDoubleTapped` and optional `enableDoubleTapZoom`.
* **Environment Control**: Added `ThreeDEnvironmentConfig` for future HDR/Environment intensity support.
* **Bug Fixes**: Improved initial loading sequence and robust tap detection across devices.

## 0.0.2

* Added `showDebugHelpers` option to display axes and grid helpers.
* Added `autoCenter` option to automatically center the model at the origin.
* Improved camera positioning and orbit controls.
* Added support for `initialTargetPosition` to specify the point the camera looks at.
* Enhanced internal load error handling.
* Fixed unused import warning in `lib/three_d_viewer.dart`.

## 0.0.1

* Initial release.
* High-performance 3D model viewing using Three.js.
* Support for GLB and GLTF formats.
* Integrated animation controls.
* Customizable camera limits and zoom configuration.
* Support for both local assets and remote URLs.
