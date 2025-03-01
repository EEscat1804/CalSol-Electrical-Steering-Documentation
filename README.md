# CalSol-Electrical-Steering-Documentation

**`In this file we will break down this image and understand what each component does. This is to help us better understand the structure of the board and what we have to do to complete it `**

<img width="515" alt="Documentation Picture" src="https://github.com/user-attachments/assets/093bd5ac-63aa-4c7b-8b5c-953f2f3af9b0" />

1) VDD33 (Power supply for the ESP32-S3-WROOM-1, 33 stands for 3.3 VOLTS)

  &nbsp;&nbsp;&nbsp;&nbsp;(C1 and C3):
  - decoupling capacitors that filters out noise and sudden voltage drops
  - C1 (22uF): bulk capacitor that smooths out fluctuations over time
  - C3 (0.1uF): high frequency capacitor that helps remove fast transient noise
    
  &nbsp;&nbsp;&nbsp;&nbsp;(R1 (TBD) & C2 (TBD)):
  - Allows us to control the EN pin
  - C2 gives us a delay when powering the board on to help ESP32 start properly
  - R1 helps regulate the voltage and make sure the pin does not float

2) USB OTG (Allows the ESP32 board to send and receive data over a USB)

   &nbsp;&nbsp;&nbsp;&nbsp;(JP3 USB Connector):
   - Pin 1 (D-) Negative signal
   - Pin 2 (D+) Positive signal
  
  &nbsp;&nbsp;&nbsp;&nbsp;(R6 & R4):
   - resistors

3) 32.768 kHz (RTC)

   &nbsp;&nbsp;&nbsp;&nbsp;(X1):
   - low frequency crystal used in RTC functions
  
   &nbsp;&nbsp;&nbsp;&nbsp;(C4 & C7):
   - 12 pF
   - capacitors that are used to stabalize crystal oscillations
  
   &nbsp;&nbsp;&nbsp;&nbsp;(R3 & R5)

4) ESP32 U1 (contains the processor, Wi-Fi, Bluetooth, and GPIOs)

   &nbsp;&nbsp;&nbsp;&nbsp;(Pins):
   - GND Connects to the ground
   - 3V3 is our 3.3V Power supply
   - EN is the enable pin
   - EPAD must be connected to GND
  
   &nbsp;&nbsp;&nbsp;&nbsp;(GPIO Pins & Functions):
   - (IO0 - IO48) -pins that can be used for multiple different tasks such as digital input/output, PWM, ADC, DAC, etc.
   - IO47 & IO48 operate in the 1.8V domain range
  
  &nbsp;&nbsp;&nbsp;&nbsp;(Communication):
  - TXD0 (Transmit Data, Pin 37)
  - RXD0 (Receives Data, Pin 36)
  - Used for UART communication

   &nbsp;&nbsp;&nbsp;&nbsp;(JTAG):
   - TMS, TDI, TDO, TCK
   - used for advanced debugging (stepping through code, memory inspection)

5) Boot & Reset Circuit (Ensures proper booting and resetting of ESP32-S3)

   &nbsp;&nbsp;&nbsp;&nbsp;SW1 (Push Button):
   - Pressing it forces a reset by pulling the EN pin to GND

   &nbsp;&nbsp;&nbsp;&nbsp;(R7):
   - Helps us get a solid electrical connection
  
   &nbsp;&nbsp;&nbsp;&nbsp;(C8):
   - 0.1 uF
   - Helps us filter out the rapid voltage change, debounces the reset switch
  
   &nbsp;&nbsp;&nbsp;&nbsp;(General Notes)
   - When SW1 is pressed:
   - EN is pulled LOW - ESP32 resets
   - EN returns HIGH - ESP 32 starts to run again
   
   


     

