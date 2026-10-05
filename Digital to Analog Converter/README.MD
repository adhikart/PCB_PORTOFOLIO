
## Overview  
  
In this directory there will be brief explanation and screen shot of PCM1792 and PCM5102 DAC
  
## Design Goal (PCM5102)
Main design goal for this DAC are mainly simplicity while retaining good audio output quality, and for this reason PCM5102 are choosen and here's why it made for good choice:
* **Simple Output Stage** it doesn't need I/V stage due to being already GND centered line level output, thanks to it's internal charge pump. This allows the chip to output a true 2.1VRMS audio signal directly, completely eliminating the need for expensive DC-blocking capacitors or an external operational amplifier (Op-Amp) stage.
*  **No Master Clock Required:** Thanks to an internal audio PLL, it can derive its own master clock directly from the I2S Bit Clock (`BCK`). This simplifies 3-wire I2S setups (like connecting to an ESP32 or Raspberry Pi) and eliminates complex external clock routing.
* **Simple PSU Implementation** PCM5102 can run with single 3.3V LDO with decent performance,but for better THD and Noise figure it's best to use two local regulator (3.3V Digital and 3.3V Analog).

## Design Goal (PCM1794)
The second iteration of this DAC are remained hardware controlled to ease the further hardware development but the goal are now toward improving the sonic quality for the DAC, and listed below are the main design goal for this second revision of the DAC:
-   **High Dynamic Range:** Deliver an wide dynamic range  to capture the quietest details and largest peaks in audio.
-   **Low Noise and Distortion:** Maintain extremely low total harmonic distortion (THD+N) for clean, transparent sound reproduction. 
-   **Balanced Current Output:** Provide current differential outputs shifting the burden of analog conversion and filtering to an external I/V (current-to-voltage) stage optimized by the designer. 
- **Hardware Control Mode** Hardware control mode provide a easy way to control DAC behavior to experiment and setup the DAC to work with the USB to I2S board.

For this reason PCM1794 are choseen for this revision while chip selection are just one part of the equation of making good DAC (other  are good layout and power supply) chip selection are also important to determine the DAC behavior and how it would interact with USB to I2S module.

## Design Approach (PCM5102)
## Design Approach (PCM1794)
<p align="center">
  <img src="./IMAGE/PCM1795_DAC.jpg" alt="CFB_F Front" width="400">
</p>

<p align="center">
  <img src="./IMAGE/PCM1795_PSU.jpg" alt="CFB_F Front" width="400">
</p>

## PCB Screenshots  (PCM5102)
## PCB Screenshots (PCM1794)
<p align="center">
  <img src="./IMAGE/DAC_3D.jpg" alt="CFB_F Front" width="400">
</p>
