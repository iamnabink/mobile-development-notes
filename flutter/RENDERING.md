In Flutter, Virtual Display and Hybrid Composition are two rendering modes used to embed platform views (native views like Android or iOS views) into a Flutter application. Both modes have their own advantages and trade-offs in terms of performance and flexibility. Let's break down the differences:
1. Virtual Display (Default on Android)
   Virtual Display is the default rendering mode used when embedding platform views in Flutter (e.g., using AndroidView or UiKitView for iOS). It creates a separate off-screen buffer for the platform view, which is then composited into the Flutter UI.
   How Virtual Display Works:
* The native platform view is rendered into an off-screen texture.
* The Flutter engine composites the texture into the Flutter UI as a widget.
  Advantages of Virtual Display:
* Performance: Virtual Display is generally more performant than Hybrid Composition because the platform view is rendered off-screen, allowing Flutter to optimize the composition process.
* Compatibility: Since it is off-screen, Virtual Display can be easily composited with Flutter widgets without much overhead.
* Less GPU Overhead: It reduces the amount of texture swapping and GPU overdraw, improving the overall frame rate.
  Disadvantages of Virtual Display:
* Limited Performance for Complex Views: For highly interactive or complex platform views (e.g., web views, maps), Virtual Display may introduce some lag due to the extra overhead of rendering off-screen and compositing.
* Visual Artifacts: There can be issues with certain widgets like videos, which may experience artifacts like flickering when scrolling.
2. Hybrid Composition (Introduced for Android)
   Hybrid Composition is an alternative rendering mode for embedding Android platform views in Flutter. Instead of rendering platform views off-screen, Hybrid Composition directly embeds the native view into the Android view hierarchy and allows it to be rendered as part of the Flutter UI.
   How Hybrid Composition Works:
* The platform view is rendered as part of the Android view hierarchy.
* Flutter uses the system's compositor to blend the platform view with Flutter UI.
  Advantages of Hybrid Composition:
* Better for Complex Platform Views: It works well with complex and interactive platform views like WebView or Google Maps, providing smoother performance.
* No Visual Artifacts: Since the platform view is directly rendered as part of the native view hierarchy, it avoids visual glitches like flickering during interactions.
  Disadvantages of Hybrid Composition:
* Performance Overhead: It is typically less performant than Virtual Display because it forces the Flutter UI to be composited together with the platform view. This can lead to more GPU overdraw and higher frame latency, especially when scrolling or resizing views.
* More GPU Usage: The direct embedding of native views increases GPU load due to the system needing to composite both Flutter widgets and native views.
  When to Use Virtual Display:
* Use Virtual Display when embedding simple native views or when you need high performance and fewer interactions.
* Good for static or less interactive platform views like banners, native ads, or smaller widgets.
  When to Use Hybrid Composition:
* Use Hybrid Composition when embedding highly interactive or complex platform views such as WebViews or Google Maps.
* Preferred when you need to avoid visual artifacts during animations, resizing, or scrolling.
  Example of Switching to Hybrid Composition (for Android):
  If you are embedding a platform view and want to enable Hybrid Composition, you need to modify your Android code. Here's how you can switch to Hybrid Composition:
  dart
  
  ```
  if (Platform.isAndroid) {
  // Enable Hybrid Composition for Android platform views
  AndroidView(
  viewType: 'your_platform_view',
  creationParams: <String, dynamic>{},
  creationParamsCodec: const StandardMessageCodec(),
  layoutDirection: TextDirection.ltr,
  gestureRecognizers: const <Factory<OneSequenceGestureRecognizer>>{},
  onPlatformViewCreated: (int id) {
  // Perform actions after platform view is created
  },
  // Use hybrid composition
  useHybridComposition: true,
  );
  }
  ```
  
* Virtual Display: Off-screen rendering, generally faster and more compatible with Flutter’s UI, but may struggle with complex or interactive views.
* Hybrid Composition: Direct embedding of platform views into the native view hierarchy, better for interactive views but comes with potential performance costs.


Flutter rendering, RenderObject is responsible for painting, gesture detection and animation

Skia is replaced by Impeller

Imepeller : Essentially, it’s a rewrite of the core rendering layer underpinning all of Flutter’s display features. Upon completion, Impeller will replace the old Skia code with custom code that can take full advantage of the latest chipsets and hardware-accelerated APIs such as Metal and Vulkan on iOS and Android.


RenderObject is base class for all flutter base UI and Render Box is implementation of RenderObject implementing it’s properies and functions like, paint, draw etc.

SchedulerBinding vs WidgetsBinding : https://stackoverflow.com/questions/56273737/schedulerbinding-vs-widgetsbinding
