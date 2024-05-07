# Functional requirements
1. Illuminate when turned on
2. Adjustable brightness levels
3. Control Wirelessly

# Non Functional requirements
1. Power efficiency
2. Long Battery life
3. Seamless user experinece

# System Architecute
1. Wireless Protocol like Zigbee, BLE or Wifi: Implement Protocol that supports mesh networking
2. Bulb design: Energy efficient LEDs, microcontroller to control brightness levels and handle communication protocols, Power management system, User Interface
3. Battery Management: Implement a battery management system and optimize charging/discharging levels.  Choose rechargeable
4. batteries with sufficient capacity.
5. Controlling device: Develop a mobile app or remote control device to communicate with the bulbs wirelessly. Make user friendly
6. interfaces to communicate with a group of bulbs.

7. Challenges:
   1. Power efficiency: Balancing brightness levels and battery levels
   2. Interference: Ensure reliable communication in environments with interference
   3. Security: Implementing robust security measures to prevent unauthorized access
   4. Scalability: Designing a system that can support a large number of bulbs without performance degradation.
   5. Integration with Smart home systems like Alexa
   6. Advanced control features like color changing or motion sensing.
  
Energy efficiency from low to high: Bluetooth Low Energy, Zigbee, Wi-Fi.
   
## BLE
* Simpler radio: BLE uses a less complex modulation scheme compared to classic Bluetooth
* Shorter transmissions: Data is sent in smaller packers, reducing overall transmission itme
* Duty Cycling: Devices spend most of their time in sleep mode, only waking up for brief periods to transmit
or receive data. 
