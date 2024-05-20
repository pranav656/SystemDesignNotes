# SPI

# I2C
I2C stands for Inter-Integrated Circuit. It is a synchronous multi-master, multi-slave packet switched serial communication protocol. It's commonly used for connecting low-speed peripherals to microcontrollers, micropocessors and other integrated circuits.  Brief overview of I2C works:
1. Master and Slave : In an I2C bus, there can be one or more master devices and one or more slave devices (sensors, EEPROM, LCD displays etc.). The master device initiates and controls the communication on bus. 
2. Serial communication: Communication in I2C occurs over two wires: Serial Data Line (SDA) and Serial Clock Line (SCL). Both lines are bidirectional allowing data to be transmitted and received.
3. Addressing: Each slave device on the bus has a unique address, allowing the master to select which device it wants to communicates with.
4. 
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

## Data formats
8N1 format (no parity) :
```
| Start Bit (0) | Data Bits (11001010) | Stop Bit (1) |
```

7E1 format (Even parity, 7 data bits) / 7O1 (Odd parity, 7 data bits)

```
| Start Bit (0) | Data Bits (1010101) | Parity Bit (0) | Stop Bit (1) |
```


# CAN

