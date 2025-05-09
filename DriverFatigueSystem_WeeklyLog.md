# Driver Fatigue System - Weekly Progress Log

### Week 1 Feb 10 - 14 | Problem Identification
Sleep-deprived driving is an underappreciated but dangerously common problem. On a recent drive back home from Illinois in my Mustang GT, I experienced firsthand just how severe fatigue behind the wheel can become. Despite having lane assist and blasting music with caffeine in hand, I caught myself swerving repeatedly—my eyelids growing heavier, my focus slipping. There were stretches of road where my eyes were closed for what felt like forever, and I realized I was becoming a serious danger to myself and everyone around me. Rest stops felt untrustworthy, and I had no meaningful way to assess whether I was safe to continue driving.

### Week 2 Feb 17 - 21 | Project Inspiration
This experience exposed a real and urgent gap in driver wellness awareness, especially when driving alone for long distances. What I truly needed wasn’t more coffee or loud music; I needed an objective, real-time system that could monitor my condition and help me make smarter decisions before it was too late.

### Week 3 Feb 24 - 28 | Project Vision
This inspired the development of the Driver Fatigue System—a multi-modal platform designed to track signs of drowsiness, monitor facial fatigue cues like prolonged blinks or yawns, and even detect signs of intoxication. By combining computer vision, real-time feedback, and onboard alerts, this system aims to support drivers in staying safe, informed, and aware of their physical state while on the road.

### Week 4 Mar 3 - 7 | Initial System Design
After identifying the dangers of drowsy driving from personal experience, we began designing a system that could monitor a driver’s alertness in real time. To do this, we needed a mix of physical sensors and wireless communication to assess wellness and deliver feedback quickly. The flowchart we developed became the blueprint for this vision, outlining how each component—camera, sensors, display, and servers—would connect and operate together.

### Week 5 Mar 10 - 14 | Integration Overview
At the heart of the system is the ESP32-S3, which collects sensor data and controls outputs like an OLED display, buzzer, and LED. Powered through a car’s USB port and regulated to 3.3V using an AMS1117, the ESP32 also connects to a DFRobot MQ-3 alcohol sensor and an OV2640 camera module. We initially planned to use a motion sensor (BNO055 IMU), but removed it after determining it was unnecessary.

### Week 6 Mar 17 - 21 | Server Communication Setup
To handle intensive tasks like image processing, we offloaded blink and yawn detection to a Raspberry Pi 4 running Python scripts and OpenCV, hosted on a Flask web server. Every 30 seconds, the Pi calculates a fatigue score and sends it back to the ESP32 or browser interface. A smartphone hotspot serves as the local network, assigning IPs to both the Pi and ESP32 for fast, local communication.

### Week 7 Mar 24 - 28 | System Impact
This system balances local device feedback with server-side intelligence, creating a responsive tool to help drivers assess their condition before it becomes dangerous, all sparked by one tired night on the road.