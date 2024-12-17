### **TrailSafe Mini Project Documentation**

---

#### **1. Problem Statement**

In disaster scenarios such as landslides or floods, locating vehicles becomes a critical challenge due to signal loss, environmental damage, and lack of robust tracking systems. The proposed solution, TrailSafe, focuses on providing a reliable and low-cost vehicle tracking system prototype suitable for such extreme conditions.

---

#### **2. Objectives of the Prototype**

1. Demonstrate the feasibility of a multi-layered tracking system.
2. Test essential features such as GPS tracking, communication via GSM, and emergency alerts.
3. Create a functional, cost-effective prototype for real-world demonstration.
4. Lay the groundwork for future development and scaling.

---

#### **3. Features Included in the Prototype**

1. **Real-Time GPS Tracking:**
   - Utilizes a low-cost NEO-6M GPS module to obtain real-time location data.
2. **GSM Communication:**
   - Sends location data to a central server or mobile device using the SIM800L module.
3. **Emergency Alerts:**
   - Activates LEDs and a buzzer during critical conditions or failures.
4. **Data Logging:**
   - Logs location and sensor data to a MicroSD card for offline retrieval.
5. **Power Supply:**
   - Powered by a rechargeable Li-ion battery for portability and reliability.

---

#### **4. Prototype Components**

| **Component**         | **Description**                               | **Estimated Cost** |
|------------------------|-----------------------------------------------|--------------------|
| **Microcontroller**   | ESP32 - Central processing and control unit.  | $6–$10           |
| **GPS Module**        | NEO-6M - Provides accurate location data.      | $8–$12           |
| **GSM Module**        | SIM800L - Enables GSM-based communication.    | $5–$10           |
| **IMU Sensor**        | MPU6050 - Tracks motion for fallback location.| $3–$5            |
| **Memory Module**     | MicroSD card module for data logging.          | $3–$5            |
| **Power Supply**      | 18650 Li-ion battery with charging module.     | $3–$8            |
| **Alert System**      | LEDs and buzzer for emergency alerts.          | $1–$3            |
| **Miscellaneous**     | Wires, breadboard, and connectors.             | $5–$10           |

**Total Estimated Cost:** $40–$60

---

#### **5. System Workflow**

1. **Normal Operation:**
   - GPS collects real-time location data and sends it to the ESP32.
                     - ESP32 transmits this data via GSM to a server or mobile device.
                        - Data is simultaneously logged onto a MicroSD card.

                        2. **Emergency Alerts:**
                           - LEDs and buzzer activate if GPS fails or communication is lost.

                           3. **Fallback Tracking:**
                              - If GPS is unavailable, the IMU sensor tracks motion and approximates location.
                                 - The last known GPS location is logged and used for recovery.

                                 ---

                                 #### **6. Assembly Guide**

                                 1. **Hardware Setup:**
                                    - Connect the NEO-6M GPS module to the ESP32 using UART (TX/RX pins).
                                       - Connect the SIM800L GSM module to another UART port for communication.
                                          - Attach the MicroSD card module via SPI for data logging.
                                             - Connect LEDs and buzzer to GPIO pins for emergency alerts.
                                                - Power everything using the 18650 Li-ion battery with a TP4056 charging module.

                                                2. **Software Configuration:**
                                                   - Use Arduino IDE to write the firmware.
                                                      - Libraries:
                                                           - `TinyGPS++` for GPS data parsing.
                                                                - `TinyGSM` for GSM communication.
                                                                     - `Adafruit MPU6050` for motion tracking.
                                                                        - Functions:
                                                                             - Read and log GPS data.
                                                                                  - Transmit location via GSM.
                                                                                       - Activate alerts during failures.
                                                                                            - Log all data to the MicroSD card.

                                                                                            ---

                                                                                            #### **7. Testing the Prototype**

                                                                                            1. **GPS Accuracy:**
                                                                                               - Test location tracking in open and obstructed environments.
                                                                                               2. **Communication Reliability:**
                                                                                                  - Verify data transmission via GSM to a mobile device or server.
                                                                                                  3. **Emergency Alerts:**
                                                                                                     - Simulate failures to test LED and buzzer activation.
                                                                                                     4. **Data Logging:**
                                                                                                        - Check the integrity of logged data on the MicroSD card.
                                                                                                        5. **Power Efficiency:**
                                                                                                           - Measure battery life during continuous operation.

                                                                                                           ---

                                                                                                           #### **8. Limitations of the Prototype**

                                                                                                           1. Rugged casing (e.g., IP68 enclosure) is not included in the prototype stage.
                                                                                                           2. Solar panel integration is excluded for cost and simplicity.
                                                                                                           3. LoRa communication is not implemented to focus on GSM.
                                                                                                           4. Advanced environmental sensors (e.g., dust, humidity) are omitted for simplicity.

                                                                                                           ---

                                                                                                           #### **9. Future Enhancements**

                                                                                                           1. Integrate LoRa communication for long-range capabilities.
                                                                                                           2. Add an IP68-rated enclosure for ruggedness.
                                                                                                           3. Include environmental sensors for comprehensive monitoring.
                                                                                                           4. Explore solar power integration for extended field operations.

                                                                                                           ---

                                                                                                           This prototype serves as a proof-of-concept for the TrailSafe system, showcasing its core functionalities and scalability for real-world applications. Let me know if you'd like additional details or diagrams!

