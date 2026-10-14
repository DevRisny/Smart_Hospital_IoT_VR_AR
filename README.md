# Smart Hospital — IoT, VR & AR Integrated Simulation

**HDIT 21132 — Emerging Technologies, Integrated Simulation Project (Individual)**

An integrated proof-of-concept for a hospital patient ward that combines three emerging technologies around one shared scenario: an **IoT** sensor/actuator network that automatically monitors and reacts to ward conditions, an interactive **VR** walkthrough for staff orientation and training, and a **WebAR** experience that lets anyone point a phone at ward equipment and instantly see what it is and how to use it.

## Problem

Patient wards that rely on manual observation react slower to unsafe conditions (temperature, humidity, smoke) than an automated system would, and staff, students and visitors have no fast, in-context way to identify ward equipment without prior training. This project simulates a connected, explorable, information-rich "Smart Hospital" ward to close both gaps.

## The three layers

| Layer | Tool | Role |
|---|---|---|
| **IoT** | Cisco Packet Tracer | Simulates the sensor/actuator network, a central gateway, and a monitoring terminal |
| **VR** | Delightex EDU | No-code, browser-based 3D walkthrough of the hospital ward |
| **AR** | MyWebAR (DEVAR CoBlocks) | WebAR builder — tap any ward object to see contextual information, no app install needed |

All three layers are built around the same ward and the same set of assets (beds, patient monitors, fire extinguishers, the emergency siren, air-conditioning/fan, and the reception area), so a user gets one consistent Smart Hospital story whether they're looking at the sensor network, walking through the VR ward, or scanning objects in AR.

## IoT network (Cisco Packet Tracer)

A star topology with a **DLC-100 Home Gateway** at the centre, connecting wirelessly to every sensor, actuator and the monitoring laptop — meeting the brief's minimum of 5+ devices, 2+ sensors, dashboard/monitoring functionality, and network connectivity between devices.

| Device | Type | Function |
|---|---|---|
| DLC100 Home Gateway | Hub / Controller | Central point connecting and coordinating every device on the ward network |
| Patient Room Temperature & Humidity Sensor | Sensor | Reports ambient temperature and humidity |
| Patient Room Smoke Detector | Sensor | Early warning for fire hazards |
| Hospital Emergency Siren | Actuator | Audible alarm to alert staff during an emergency |
| Patient Room Smart Light | Actuator | Remotely/automatically controlled room lighting |
| Patient Room Smart Fan | Actuator | Remotely/automatically controlled air circulation |
| Laptop-PT | Monitoring terminal | Runs the IoT Monitor app to view/manage the whole network |

An automation rule ties the safety sensors to the actuators so the ward reacts without a staff member present — smoke from the Smoke Detector automatically triggers the Emergency Siren, and temperature/humidity readings automatically switch the Smart Fan and Smart Light to keep the room comfortable.

## VR walkthrough (Delightex EDU)

An interactive 3D walkthrough of the ward with clickable hotspots on every major asset, describing what it is and how it's used — built for staff and student orientation/training.

## AR experience (MyWebAR)

A WebAR scene of the same ward, accessible via a shareable link and QR code with no dedicated mobile app required. Tapping a piece of furniture or equipment instantly surfaces the same contextual information as the VR hotspots, at the point of need.

## Scope

A proof-of-concept limited to a single patient ward area (two patient bed sections, a reception/waiting area, and an attached washroom). The IoT component is simulated entirely within Cisco Packet Tracer (not deployed on physical hardware); it does not connect to a real hospital information system or electronic health record.

## Repository contents

```
packet-tracer/
  Smart_Hospital_IoT.pkt              Cisco Packet Tracer source file — open with
                                       Packet Tracer 8.2.2+ to explore/simulate the
                                       live IoT network described above
docs/
  HDIT-B1-027_Smart_Hospital_EM_Report.pdf   Full project report (7 chapters: Introduction,
                                              Proposed Solution, IoT Simulation, VR Simulation,
                                              AR Simulation, Integration, Conclusion)
diagrams/
  City_Hospital_ER_Diagram.png  Supporting database/entity diagram for the ward scenario
  SmartHospital_QR.png          QR code linking to the AR experience
```

The VR and AR projects live in their respective platforms, and the demo video (~430 MB, too large for GitHub) is hosted on OneDrive — none of these are distributable as plain repo files:

- **VR (Delightex EDU):** edu.delightex.com/RLP-BQU
- **AR (MyWebAR):** mywebar.com/p/Project_0_zo25pog188
- **Demo video:** [City Hospital_Demo.mp4 (OneDrive)](https://icstechnologycampus-my.sharepoint.com/:v:/g/personal/03241035_icst_edu_lk/IQAxfat--jweSLaI0jM8dFwLAdBoh0Mzb1NvkqldqcVJIm8)

## Author

Miss. Junaideen Risny Suha — Student ID 03241035 — Higher Diploma in Information Technology, ICST
