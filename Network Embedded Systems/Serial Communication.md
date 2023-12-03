![[Pasted image 20231203170440.png]]

![[Pasted image 20231203170525.png]]


![[Pasted image 20231203170727.png]]

Prescalar:
A **prescaler** is an electronic [counting circuit](https://en.wikipedia.org/wiki/Counter_(digital) "Counter (digital)") used to reduce a high [frequency](https://en.wikipedia.org/wiki/Frequency "Frequency") electrical signal to a lower frequency by [integer division](https://en.wikipedia.org/wiki/Integer_division "Integer division"). The prescaler takes the basic timer clock frequency (which may be the CPU clock frequency or may be some higher or lower frequency) and divides it by some value before feeding it to the timer, according to how the prescaler register(s) are configured. The prescaler values, referred to as prescales, that may be configured might be limited to a few fixed values (powers of 2), or they may be any integer value from 1 to 2^P, where P is the number of prescaler bits.


Bit banging:
In [computer engineering](https://en.wikipedia.org/wiki/Computer_engineering "Computer engineering") and [electrical engineering](https://en.wikipedia.org/wiki/Electrical_engineering "Electrical engineering"), **bit banging** is a "[term of art](https://en.wikipedia.org/wiki/Term_of_art "Term of art")" for any method of [data transmission](https://en.wikipedia.org/wiki/Data_transmission "Data transmission") that employs software as a substitute for dedicated hardware to generate transmitted signals or process received signals. Software directly sets and [samples](https://en.wikipedia.org/wiki/Sampling_(signal_processing) "Sampling (signal processing)") the states of [GPIOs](https://en.wikipedia.org/wiki/GPIO) (e.g., pins on a [microcontroller](https://en.wikipedia.org/wiki/Microcontroller "Microcontroller")), and is responsible for meeting all timing requirements and protocol sequencing of the signals. In contrast to bit banging, dedicated hardware (e.g., [UART](https://en.wikipedia.org/wiki/UART "UART"), [SPI](https://en.wikipedia.org/wiki/Serial_Peripheral_Interface "Serial Peripheral Interface"), [I²C](https://en.wikipedia.org/wiki/I%C2%B2C "I²C")) satisfies these requirements and, if necessary, provides a [data buffer](https://en.wikipedia.org/wiki/Data_buffer "Data buffer") to relax software timing requirements. Bit banging can be implemented at very low cost, and is commonly used in some [embedded systems](https://en.wikipedia.org/wiki/Embedded_systems "Embedded systems").[[1]](https://en.wikipedia.org/wiki/Bit_banging#cite_note-Predko_2000-1)



UART Peripheal: w4 example of a uart peripheral
**8-N-1** is a common shorthand notation for a [serial port](https://en.wikipedia.org/wiki/Serial_port "Serial port") parameter setting or [configuration](https://en.wikipedia.org/wiki/Computer_configuration "Computer configuration") in [asynchronous](https://en.wikipedia.org/wiki/Asynchronous_start-stop "Asynchronous start-stop") mode, in which there is one start bit, eight (**8**) [data bits](https://en.wikipedia.org/wiki/Bit "Bit"), no (**N**) [parity bit](https://en.wikipedia.org/wiki/Parity_bit "Parity bit"), and one (**1**) [stop bit](https://en.wikipedia.org/wiki/Stop_bit "Stop bit").[[1]](https://en.wikipedia.org/wiki/8-N-1#cite_note-modemhelp-1) As such, 8-N-1 is the most common configuration for [PC](https://en.wikipedia.org/wiki/Personal_computer "Personal computer") serial communications today.

CPOL & CPHA:
CPOL and CPHA (for **c**lock **pol**arity and **c**lock **pha**se)

SDA:
Serial Data
SCL:
Serial Clock

![[Pasted image 20231203200342.png]]