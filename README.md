# StarkGesture

A futuristic browser-based hand gesture interface that uses real-time hand tracking to control a holographic sphere.

StarkGesture combines **MediaPipe Hand Landmarker**, **Vanilla JavaScript**, **HTML Canvas**, and modern **Web APIs** to create an interactive computer-vision experience directly in the browser.

## Features

* Real-time hand tracking through the device camera
* Hand landmark visualization
* Gesture recognition using MediaPipe
* Gesture-based object interaction
* Smooth sphere movement and scaling
* 3D-style sphere rotation
* Particle effects and visual feedback
* Audio feedback for the sphere explosion effect
* Live telemetry including:

  * Hand count
  * Detected gesture
  * Confidence
  * FPS
  * Vision engine status
* Responsive interface for smaller screens
* Camera access and error handling
* Reduced-motion support
* Keyboard demo mode for testing gestures without using the camera

## Supported Gestures

| Gesture                     | Action                         |
| --------------------------- | ------------------------------ |
| Thumb + Index Pinch         | Move the sphere                |
| Thumb + Middle Finger Pinch | Zoom in / out                  |
| Point Up + Twist            | Move and rotate the sphere     |
| Fist                        | Trigger the particle explosion |
| No Gesture                  | Return to idle state           |

## Tech Stack

* HTML5
* CSS3
* Vanilla JavaScript
* MediaPipe Tasks Vision
* Hand Landmarker
* HTML Canvas API
* Web Camera API (`getUserMedia`)
* Web Audio API
* `requestAnimationFrame`

## How It Works

The application requests access to the user's camera and uses **MediaPipe Hand Landmarker** to detect hand landmarks in real time.

The detected landmark coordinates are then processed by JavaScript to identify different hand poses and calculate interaction data such as:

* Finger extension
* Pinch distance
* Hand position
* Wrist rotation
* Zoom movement

A small gesture state machine helps stabilize gesture changes before triggering actions. The resulting interaction data is used to control the holographic sphere and its visual effects.

## Running Locally

Clone the repository and open the project through a local development server.

```bash
git clone https://github.com/YOUR-USERNAME/stark-gesture.git
cd stark-gesture
```

Then serve the project locally using any simple HTTP server.

For example:

```bash
python -m http.server 8000
```

Open:

```text
http://localhost:8000
```

Allow camera access when prompted.

## Demo Mode

StarkGesture also includes a keyboard-based demonstration mode.

When the camera is not active, use:

```text
1 → Move Pinch
2 → Zoom Pinch
3 → Point Up
4 → Fist
5 → None
```

This makes it possible to demonstrate the interface without requiring camera input.

## Privacy

Camera frames are processed on the client side by the application. The project does not implement a backend service or upload camera footage to a server.

The application does load the MediaPipe library, WASM runtime, and hand-tracking model from external CDNs when initializing the vision engine.

## Project Structure

The project is intentionally implemented as a compact single-page application.

```text
stark-gesture/
└── index.html
```

The main file contains the interface, styling, application state, gesture recognition logic, camera handling, rendering, animations, and interaction system.

## Project Goal

This project was created as a personal portfolio project to explore:

* Frontend development
* Browser APIs
* Computer vision in the browser
* Real-time interaction
* Canvas rendering
* Animation systems
* Human-computer interaction

## AI Assistance
AI tools were used as development assistance during the implementation of this project.

## Status

**Completed portfolio project**

The project is designed primarily as an interactive technical demonstration and portfolio piece.

## License

This project is available for personal and educational use.
