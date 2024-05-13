# SPI

# I2C

# I3C

# UART
UART stands for universal Asynchronous Receiver/Transmitter. It's a communication protocol used in serial communication between two devices.  UART enables data transmission between devices using two wires: one for transmission (Tx) and the other for receving data (Rx). It operates asynchronously, meaning the data is senbt without a shared clock signal. Instead both devices agree on a baud rate (bits per second). UART is widely used in embedded systems, computer peripherals, and various devices for serial communication. 
Communication starts with a start bit, which indicates hte beginning of a data froame. It has a logic low (0) voltage level. 
Data bits: These are the actual bits of data being transmitted. LSB is sent first.
Parity Bit(optional): This bit can be used for error checking. It is set to a value that ensures that total number of logic bits in the data frame (including start, data and stop bits) is either even or odd.
Stop bits: One or more stop bits follow data bits. The stop bits indicate the end of a data frame and have a logic high (1) voltage level. 

Transmitter side code using pyserial libarary:
```
import serial
import time

# Define serial port settings
port = '/dev/ttyUSB0'  # Adjust this to your serial port
baud_rate = 9600

# Open serial port
ser = serial.Serial(port, baud_rate)

try:
    # Continuously send data
    while True:
        data_to_send = "Hello, UART!"
        ser.write(data_to_send.encode())  # Convert string to bytes and send
        print(f"Sent: {data_to_send}")
        time.sleep(1)  # Wait for a second
        
except KeyboardInterrupt:
    print("\nProgram terminated by user.")

finally:
    ser.close()  # Close serial port
````

Receiver side code:

```
import serial

# Define serial port settings
port = '/dev/ttyUSB0'  # Adjust this to your serial port
baud_rate = 9600

# Open serial port
ser = serial.Serial(port, baud_rate)

try:
    # Continuously read data
    while True:
        received_data = ser.readline().decode().strip()  # Read and decode incoming bytes
        print(f"Received: {received_data}")

except KeyboardInterrupt:
    print("\nProgram terminated by user.")

finally:
    ser.close()  # Close serial port

````

# CAN

