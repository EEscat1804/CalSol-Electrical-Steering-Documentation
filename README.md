# CalSol-Electrical-Steering-Documentation

**`In this file we will break down this image and understand what each component does. This is to help us better understand the structure of the board and what we have to do to complete it `**

<img width="515" alt="Documentation Picture" src="https://github.com/user-attachments/assets/093bd5ac-63aa-4c7b-8b5c-953f2f3af9b0" />

1) VDD33 (Power supply for the ESP32-S3-WROOM-1, 33 stands for 3.3 VOLTS)

  &nbsp;&nbsp;&nbsp;(C1 and C3):
  - decoupling capacitors that filters out noise and sudden voltage drops
  - C1 (22uF): bulk capacitor that smooths out fluctuations over time
  - C3 (0.1uF): high frequency capacitor that helps remove fast transient noise
    
  &nbsp;&nbsp;&nbsp;(R1 (TBD) & C2 (TBD)):
  - Allows us to control the EN pin
  - C2 gives us a delay when powering the board on to help ESP32 start properly
  - R1 helps regulate the voltage and make sure the pin does not float

2) USB OTG (Allows the ESP32 board to send and receive data over a USB)

   (

