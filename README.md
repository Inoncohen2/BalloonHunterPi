# BalloonHunterPi

![Demo GIF](images/Balloon_detection.gif)

🎓 **BalloonHunterPi** is an autonomous system for detecting, tracking, and intercepting balloons in real-time. This project combines advanced technologies in image processing, artificial intelligence, and motion control, designed as part of my final engineering project.

---

## Table of Contents
1. [About the Project](#about-the-project)
2. [System Architecture](#system-architecture)
3. [How It Works](#how-it-works)
4. [Development Process](#development-process)
5. [Key Challenges](#key-challenges)
6. [Main Results](#main-results)
7. [Applications](#applications)
8. [Future Improvements](#future-improvements)
9. [Images and Videos](#images-and-videos)
10. [Acknowledgments](#acknowledgments)

---

## About the Project
The BalloonHunterPi system was designed to autonomously detect, track, and intercept balloons in motion. The project combines cutting-edge technologies in AI, computer vision, and control systems, running on the Raspberry Pi platform.

---

## System Architecture
The system comprises three main modules:
1. **Video Input Module**  
   - A high-resolution USB camera captures live video input for real-time processing.

2. **Object Detection and Analysis Module**  
   - TensorFlow Lite processes video frames to identify balloons.  
   - The system converts pixel-based coordinates to angles for motor control.

3. **Motion Control Module**  
   - Servo motors precisely aim a laser pointer at the detected balloon's position.  
   - A safety mechanism ensures the laser activates only when a clear target is identified.

**[Add a complete architecture diagram here, showing hardware connections and system workflow]**

---

## How It Works
1. **Real-Time Video Input**  
   A high-resolution USB camera streams live video to the Raspberry Pi.  
   **[Add an image of the camera in action]**

2. **Detection and Data Processing**  
   - TensorFlow Lite detects balloons in the video frames.  
   - The system calculates the balloon's location in pixels and converts it into angles for motor positioning.  

   **[Add a screenshot of a detected balloon with a bounding box]**

3. **Motor Control**  
   Servo motors adjust the laser pointer's position based on the detected angles.  
   **[Add a flowchart showing the data processing and motor control pipeline]**

---

## Development Process
- **Data Collection and Labeling**:  
  Hundreds of balloon images were collected and labeled using tools like LabelImg.  

- **Model Training**:  
  - The model was trained in Google Colab using the TensorFlow Object Detection API.  
  - Data was converted to TFRecord format for training.  

**[Add training graphs like Total Loss and Localization Loss]**

- **Initial Testing**:  
  The system was tested for detection accuracy, motor responsiveness, and real-time tracking.

---

## Key Challenges
1. **Real-Time Processing on Raspberry Pi**  
   Optimizations were required to handle the Raspberry Pi's limited processing power effectively.

2. **Servo Motor Calibration**  
   Hours of trial and error were spent to ensure precise angle conversions for accurate targeting.

3. **Handling Dynamic Environments**  
   The system was designed to detect balloons under varying colors, lighting conditions, and distances.

---

## Main Results
- **High Detection Accuracy**:  
  The system consistently identifies balloons under diverse conditions.  

- **Smooth and Accurate Tracking**:  
  The laser pointer remains focused on the balloon even during movement.  

- **Robust Safety Mechanism**:  
  The laser is deactivated automatically when no balloon is detected.  

**[Add an image showing the system detecting and tracking balloons in real-time]**

---

## Applications
- **Security**:  
  Autonomous tracking and interception of drones or other aerial threats.  

- **Robotics and Automation**:  
  Enhancing tracking and detection systems for industrial applications.  

- **Education and Science**:  
  Interactive demonstrations for teaching and research purposes.  

---

## Future Improvements
- **Hardware Acceleration (Google Coral)**:  
  Integrating hardware accelerators to enhance processing speed.  

- **Upgrading to YOLO Model**:  
  Using YOLO for faster and more accurate object detection.  

- **Improved Servo Motors**:  
  Upgrading motors for better stability and faster response.  

---

## Images and Videos

### **System in Action**
**[Add an image of the full system setup, including the camera, motors, and laser pointer]**

### **Balloon Detection**
**[Add an image or GIF showing real-time balloon detection and tracking]**

### **Demo Video**
Watch the system in action:  
[YouTube - System Demo](https://www.youtube.com/your_demo_video)

---

## Acknowledgments
Special thanks to my supervisor, friends, and family for their support throughout the development process.  

---
