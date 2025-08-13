# 👁️ Youth Vision Protection App

## 📌 Project Overview
The **Youth Vision Protection App** is an Android application designed to measure the distance between the user's face and the smartphone screen in real-time.  
When the distance is too short, the app warns the user and can either dim the screen, apply blur effects, or block the screen to prevent eye strain.  
This project aims to **prevent vision deterioration in youth** and promote **healthy smartphone usage habits**.

## 👨‍💻 Team Members
- **Taehee Ko** – UI design, app structure, Mediapipe integration
- **Joohyung Kim** – Distance calculation logic, CameraFragment development
- **Daun Lee** – Feature development & integration
- **Sechan Pi** – Distance threshold warning & Toast notification logic

## 🚀 Features
- 📱 **UI Implementation** – Simple and intuitive interface
- 📷 **Camera Integration** – Real-time camera feed for face tracking
- 🧠 **Face Landmark Detection** – Using [Mediapipe Face Landmarker](https://github.com/google-ai-edge/mediapipe-samples/tree/main/examples/face_landmarker/android)
- 📏 **Distance Measurement** – Calculates face-to-screen distance using eye landmark points
- ⚠️ **Distance Warning** – Displays a message when the distance is below the threshold
- 🔒 **Screen Control** – Dim or blur the screen when too close
- ⚙️ **Background Execution** – Camera runs in the background to ensure constant monitoring

## 📂 Project Structure
app/
├── MainActivity.java # Brightness control example  
├── CameraFragment.kt # Camera + FaceMesh + Distance calculation  
├── fragment_facemesh.xml # FaceMesh fragment UI  
├── res/layout/ # App UI layouts  
└── ...  

## 🛠 Tech Stack
- **Development Environment**: Android Studio
- **Languages**: Java / Kotlin
- **Libraries**: [Mediapipe](https://developers.google.com/mediapipe) (`face_landmarker`)
- **Platform**: Android

## 📷 Screenshots
- **Start Screen** – Logo and navigation buttons  
- **Main Screen** – Live camera feed with real-time distance display  
- **Warning Example** – Toast message when too close

*(Screenshots and UI preview images can be added here)*

## 💡 Example Code Snippet
- **Distance Warning**
  if (distance < 30) { 
    Toast.makeText(this, "Distance is less than 30cm!", Toast.LENGTH_SHORT).show()
}

- **Distance Calculation**
  val perceivedDistanceInPixels = calculateDistance(
    leftEyeXPixel, leftEyeYPixel, rightEyeXPixel, rightEyeYPixel
)
val distanceCm = (KNOWN_DISTANCE_BETWEEN_EYES * FOCAL_LENGTH_PIXEL) / perceivedDistanceInPixels

