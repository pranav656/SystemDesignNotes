# System Architecture

## Hardware
* Camera 
* Microphone and speaker for two way communication
* Motion sensors
  * PIR : Passive Infrared is a type of sensor used to detect motion by measuring infrared light
  radiating from objects in it's field of view. All objects emit IR, the level depends on the temperature. PIR
  sensors are designed to detect changes in infrared radiation levels in their environment. The core of PIR consists   of pyroelectric material that generates an electric charge in response to IR. When an object moves within the
  sensor's range, it causes a change in the amount of infrared radiation detected by the pyroelectric material. A fresnel lens is often placed in front of the sensor element to focus the IR radiation onto the pyroelectric material and to expand the sensor's field of view. The range is typically limited to a few meters.
* Wi-Fi module: Ensure compatibility with common Wi-Fi standards (802.11)
* Power : Design for low power consumption. Use a rechargeable battery with solar panel support for extended battery
life.
* Processor : Use a processor capable of handling video compression (eg.H.264), motion detection algorithms and
real-time data transmission.

## Software Design
* Firmware:
  * Handle video streaming, encoding and uploading to the cloud.
  * Implement efficient motion detection algorithms to reduce false positives.
  * Manage two-way audio communication
  * Provide secure communication with cloud services using encryption.
 
* Mobile application:
  * Live stream with two way audio
  * User registration and Login (OAuth or similar authenitcation mechanisms).
  * Real-time notifications for motion detection or doorbellpress.
  * Access to stored video footage.
  * Update device settings like motion sensitivity, video preferences etc.

* Cloud services:
  * Video storage: Store video clips securely, with options for retrieval and playback.
  * Processing: Implement features like motion detection, facial recognition and object classification.
  * Notifications: Push notifications to mobile devices. Enables real time alerts like motion detection, door bell press etc.

* Web Portal:
  * Provide access to live and recorded footage.
  * Manage device settings and user accounts.
  * Offer analytics and reporting on motion detection events.
 
## Security considerations
* Data encryption: Encrypt video streams and stored footage to protect user privacy
* Authentication: Use strong authenication mechanisms to prevent unauthorized access.
* Firmware updates: Implement secure over the air updates to patch vulnerabilities.

## Integration with smart home ecosystems
* Ensure compatibility with home systems like Alexa, Google Home.
* Implement APIS for integration with home automation systems

## UI and design
* Ease of installation: Provide a straight forward installation process, including mounting process and setup wizard in the mobile app.
* Design and intuitive and user friendly interface for both the mobile app and web portal
* Ensure system is available with minimal downtime, and provide clear indicators for battery status and connectivity issues.

## Testing and QA
* Functional tesing: Verify all features work as expected including video quality, motion detection and two-way
communication.
* Performance testing: Ensure system performs well under various network conditions.
* Security Testing: Conduct thorough security audirs to identify and fix vulnerabilities.
