# Spidey-Draw

## Summary

SpideyDraw is an automated drawing robot designed to reproduce digital images on physical surfaces with precision and efficiency. The system integrates art and technology by combining a mobile application with a mechanical robot that translates uploaded digital sketches into real drawings.

It operates using a square frame equipped with four stepper motors and a servo-controlled pen, enabling smooth and controlled movement across the drawing area. This project serves as an innovative, educational, and low-cost platform for learning robotics, control systems, and mechatronics.

---

## Problems

* Traditional drawing or plotting methods rely heavily on manual work, which can be slow and inconsistent.
* Lack of portable and flexible systems that can easily connect to modern devices like smartphones for interactive use.

---

## Challenges

* Maintaining drawing accuracy across different surface sizes.
* Synchronizing mechanical and electronic components required precise calibration.
* Ensuring stable pen movement without vibration or deviation.

---

## Problem Solved

* SpideyDraw provides a lightweight, affordable, and easy-to-use robotic drawing system.
* The robot receives an image from a mobile app via Wi-Fi, processes it into coordinate paths, and accurately reproduces it using stepper motors and a servo-controlled pen.

---

## Mobile Application & Image Processing


### Mobile Application

SpideyDraw includes a mobile application that provides a smooth and interactive interface for controlling the drawing process.

The application allows users to:

* Upload images from their device
* Preview selected images before processing
* Convert images into drawable paths
* Send processed data to the robot via Wi-Fi
* View processing results such as number of strokes and total drawing length

The design focuses on simplicity and usability, guiding users through a clear workflow from image selection to execution.

---

### Image Processing Pipeline

The system uses a custom pipeline to convert images into coordinate-based paths suitable for robotic drawing.

#### Steps

1. **Image Upload**
   The user selects an image using the mobile application.

2. **Preprocessing**

   * Convert the image to grayscale
   * Apply edge detection to extract outlines

3. **Path Extraction**

   * Detect key points (vertices)
   * Convert edges into connected line segments

4. **Optimization**

   * Reduce redundant points
   * Organize paths to minimize unnecessary movement

5. **Output Generation**

   * Convert paths into (X, Y) coordinates
   * Calculate total drawing length
   * Count the number of strokes

---

### Backend Server

A backend server handles image processing and communication between the mobile application and the robot.

#### Responsibilities

* Receive images from the mobile application
* Process images using image processing algorithms
* Convert images into coordinate paths
* Send processed data back to the application
* Handle communication with the robot

#### Technologies Used

* Python for image processing
* REST APIs for communication
* Wi-Fi for transmitting data to the robot

---

### Robot Communication

After processing:

* The mobile application sends coordinate data to the robot
* The robot translates coordinates into movement commands
* Stepper motors control X and Y movement
* A servo motor controls pen up and down actions

---

### Processing Output Example

* Number of strokes: 27
* Total drawing length: 4340 px

The system also displays:

* Original image
* Processed drawing paths

---

## Demo


### Video 
The video demonstrates:

* Uploading an image
* Processing it
* Sending it to the robot
* The robot drawing the final output

https://github.com/user-attachments/assets/d1cd4493-7d35-4bc6-91aa-35f840f17d6b


### Screenshots

#### Get started screen

![WhatsApp Image 2026-04-13 at 7 21 58 AM(2)](https://github.com/user-attachments/assets/ad63b276-85ee-4ab2-a884-a48432e78a8e)

#### Upload Screen

![WhatsApp Image 2026-04-13 at 7 21 58 AM(1)](https://github.com/user-attachments/assets/04f3e815-ff07-4faa-aa11-a848008c58a0)

#### Image Preview

![WhatsApp Image 2026-04-13 at 7 21 58 AM](https://github.com/user-attachments/assets/e0ed1fa6-ccfd-4fc4-b5f1-2b99676cb992)

#### Processed Image

![WhatsApp Image 2026-04-13 at 7 21 59 AM(2)](https://github.com/user-attachments/assets/3975b289-e8de-4f58-88f0-2ff482be4559)

#### Compass generating orders to move

![WhatsApp Image 2026-04-13 at 7 21 58 AM(3)](https://github.com/user-attachments/assets/60429d7c-fac2-432d-8401-35be01e8c5a3)

![WhatsApp Image 2026-04-13 at 7 21 59 AM(1)](https://github.com/user-attachments/assets/53a36dbf-d559-4f3b-86b4-1bc8324764d8)

![WhatsApp Image 2026-04-13 at 7 21 59 AM](https://github.com/user-attachments/assets/bbf445df-fde0-4a94-819d-e08310d24404)


---


## Hardware

* 4 Stepper Motors (5V 28BYJ-48)
* 4 ULN2003 Motor Drivers
* NODEMCU-32 v1.3
* MG996R Servo Motor
* 4 Caster Wheels
* 4 Limit Switches
* PCB
* Pin Headers
* Connectors (USB Type B)
* Capacitors and Resistors
* Screws and Nuts
* 3D Printed Spools

---
## Images of the robot

<img width="1058" height="795" alt="unnamed" src="https://github.com/user-attachments/assets/0313f72f-631d-442a-a8cd-6a8fa9d3fd2d" />

<img width="1065" height="891" alt="2" src="https://github.com/user-attachments/assets/1bdfcace-f2ff-45dc-97fc-863b272a0b58" />

<img width="916" height="600" alt="2" src="https://github.com/user-attachments/assets/d3851c28-9480-4e24-aed6-2e3216c0515d" />

---
## Future Improvements

* Support for shaded drawings instead of only line-based sketches
* Integration of AI-based image simplification
* Real-time drawing simulation before execution
* Offline processing without requiring a server
* Improved speed and accuracy of path planning
