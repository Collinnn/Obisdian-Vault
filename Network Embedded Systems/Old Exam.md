

Q1:
D. Batteries build internal resistance that limits the maximum current they can source.

Explanation: A. This statement is generally false. While resistors are manufactured to have specific resistance values, there can still be variations, and the measured resistances may not be identical. B. This statement is false. The output voltage from an AC-DC converter is not necessarily constant; it depends on the specific converter and its design. C. This statement is true. A voltage divider can be used to scale down a voltage signal. However, the example given is shifting a 3.3V signal to a 5V signal, which is not accurate. A voltage divider can be used to obtain a fraction of the input voltage, but it doesn't shift the voltage level. To shift a voltage level, an additional circuit, such as an op-amp circuit, is needed. D. This statement is true. Batteries have internal resistance due to the materials and construction used in their design. This internal resistance limits the maximum current they can provide, and it also contributes to energy loss in the form of heat when the battery is discharged.

Q2:
![[Pasted image 20231205201721.png]]

Q3
C. I2C

Explanation: I2C (Inter-Integrated Circuit) is a serial communication protocol that uses identification numbers, known as device addresses, to specify the peripheral devices on the bus. Each device connected to an I2C bus has a unique address, and communication occurs between the master (initiating device) and a specific slave (peripheral) based on these addresses.

In contrast:

- UART (Universal Asynchronous Receiver-Transmitter) is a simple serial communication protocol that doesn't inherently use device addresses.
- SPI (Serial Peripheral Interface) also does not use device addresses in the same way as I2C. Instead, it typically uses a chip select (CS) signal to select the desired peripheral.
- GPIO (General Purpose Input/Output) is not a serial communication protocol; it refers to pins on a microcontroller or other digital device that can be configured as inputs or outputs for general-purpose digital signaling.


Q4:
In the CAN (Controller Area Network) protocol, lower numerical values of the identifier have higher priority. The identifier is transmitted as a sequence of bits, and in the case of tie-breaking, the device with the lower binary value has higher priority.

Let's compare the binary representations of the given IDs:

A: 10101010101 B: 11101110111 C: 11011011011 D: 11110111101

Comparing the leftmost bits: A has the lowest leftmost bit. Therefore, A has the highest priority.

So, the correct answer is: A. A

Q5:
  
D. Duty Cycling based on a wakeup radio

Explanation: When designing a wireless communication system with the goal of maximizing the battery lifetime of a sensor, duty cycling is a common technique. Duty cycling involves turning off the radio for most of the time and only turning it on periodically to transmit or receive data. This minimizes the energy consumption during idle periods.

In this context, the option "D. Duty Cycling based on a wakeup radio" specifically mentions the use of a wakeup radio. A wakeup radio is a low-power, separate radio that is always on and continuously monitors for a specific signal or event. When the sensor needs to communicate, it sends a wakeup signal using the low-power wakeup radio, and the main radio is activated only during the active communication period. This approach can significantly reduce the overall energy consumption compared to keeping the main radio always on or using continuous active scanning.

Options A, B, and C (CSMA/CA, Duty-Cycled CSMA/CA, Synchronous MAC based on time slots) are techniques related to managing the medium access control (MAC) layer in wireless communication, but they may not be as power-efficient as duty cycling with a wakeup radio when the goal is to maximize battery lifetime.

Q6:
The second least significant bit in a binary representation is typically at position 1 (using zero-based indexing). Therefore, to toggle the second least significant bit of an 8-bit register (REG), you would XOR it with the value where only the bit at position 1 is set to 1.

The correct statement is: B. REG = (0x01 << 1) ^ REG;

This statement shifts the bit 0x01 to the left by 1 position, creating a value with only the second least significant bit set to 1, and then XORs it with the current value of REG, effectively toggling the second least significant bit.

Q7:
  
Minimizing active power consumption is more important than minimizing idle power consumption in applications where the device is frequently in an active state and actively performing tasks. In scenarios where the device spends a significant amount of time in an active or transmitting state, the power consumed during these active periods becomes crucial.

Given the options:

C. A wearable sensor capturing continuous high-frequency health-oriented data.

In wearable sensors capturing continuous high-frequency health-oriented data, the device is likely to be frequently active, collecting and transmitting data. In such cases, minimizing the power consumption during active periods is crucial for extending the battery life and ensuring the device's continuous operation. Idle power consumption may still be important, but in this context, active power consumption takes precedence.

Therefore, the correct answer is C. A wearable sensor capturing continuous high-frequency health-oriented data.

Q8:
  
D. A way to eliminate time synchronization problems in networks embedded systems is to measure the drift of their clocks and calibrate it with a constant adjustment.

Explanation: The statement D is false. While it's true that measuring clock drift and applying adjustments can help in time synchronization, stating that it's a way to "eliminate" time synchronization problems might be an overstatement. Clock drift can be affected by various factors, and while adjustments can compensate for some of the drift, it may not completely eliminate synchronization issues, especially in scenarios with rapidly changing conditions or in systems with stringent timing requirements.

The other statements are generally true:

A. Periodic time synchronization is indeed needed because clocks used by embedded systems can drift over time, leading to a divergence from each other and from UTC (Coordinated Universal Time).

B. GPS is commonly used for time synchronization because the satellites have highly accurate atomic clocks. The signals from the GPS satellites provide precise time references.

C. PTP (Precision Time Protocol) is designed for high-precision time synchronization in local area networks and takes timestamps at the hardware level to achieve better performance compared to NTP (Network Time Protocol). PTP and NTP, while having similar goals, differ in their approach and accuracy.

Q9:
B. Collisions in TSCH are impossible.

Explanation: The statement B is false. While Time-Slotted Channel Hopping (TSCH) is designed to reduce the likelihood of collisions through its time synchronization and channel hopping mechanisms, it does not make collisions impossible. Collisions can still occur in TSCH, especially in scenarios with high network traffic, changes in network topology, or other challenging conditions. TSCH provides mechanisms to mitigate collisions, but it cannot guarantee their complete elimination.

The other statements are generally true:

A. TSCH uses channel hopping to avoid external interference and to improve reliability by utilizing different channels.

C. In TSCH, each device periodically synchronizes its clock with its time source to maintain accurate time slots for communication.

D. TSCH supports multi-hop networks, allowing devices to relay messages through intermediate devices to extend the network coverage.

Q10:
B. Embedded AI is typically more accurate than cloud-based AI.

Explanation: The statement B is false. The accuracy of AI models does not inherently depend on whether they are deployed in embedded systems or in the cloud. The accuracy of an AI model is primarily determined by the quality of the model itself, the training data, and the training process. Both embedded AI and cloud-based AI can achieve high accuracy if well-designed and trained.

The other statements are generally true:

A. Embedded AI often has lower latency compared to cloud-based AI because it processes data locally on the device, reducing the need for data transfer to and from the cloud.

C. Embedded AI can be more private than cloud-based AI because it processes data on the device, avoiding the need to send sensitive information to external servers.

D. Embedded AI is typically more resource-efficient than cloud-based AI because it operates on local hardware, minimizing the need for continuous internet connectivity and reducing dependence on cloud resources.