# 32_band_frequency_spectrum_visualizer

## Overview
This project implements an **Audio Spectrum Visualizer** using an **Arduino Nano** and an **8x32 LED matrix display**. It leverages the **Fast Fourier Transform (FFT)** algorithm to analyze real-time audio signals and represent their frequency spectrum visually. The project is an affordable alternative to commercial audio spectrum analyzers, allowing users to analyze sound characteristics, diagnose audio equipment issues, and explore signal processing interactively.

## Features
- Real-time audio frequency analysis using the **ArduinoFFT** library.
- **32-band frequency visualization** on an **8x32 LED matrix**.
- Multiple display modes:
  - **Linear scale representation** for uniform frequency distribution.
  - **Logarithmic scale representation** for human-auditory perception alignment.
- Audio input through an **aux cable** for minimal noise interference.
- Adjustable sampling rate with **Nyquist theorem compliance** for accurate frequency representation.

## Components Used
- **Arduino Nano (ATmega328P)**
- **8x32 LED Matrix Display**
- **Auxiliary (AUX) Cable**
- **Resistors)**
- **Capacitors**
- **Push Button (Mode Switching)**

## Circuit Design
### Audio Signal Processing:
- The analog audio signal (from AUX input) is **DC shifted** using a voltage divider to match the Arduino's ADC (0-5V input range).
- The **ADC samples** the signal at **38.46 kHz**, ensuring accurate frequency analysis up to **19.32 kHz** (Nyquist theorem).
- The **ArduinoFFT library** is used to process the sampled audio and extract frequency components.

### LED Matrix Display:
- The **MD_MAX72xx library** manages the LED matrix, enabling efficient visualization of frequency bands.
- The amplitude of each frequency band is mapped to the **LED column height**, providing an intuitive graphical representation.
- A **push button** allows users to toggle between **linear and logarithmic display modes**.

## Software Implementation
1. **Analog-to-Digital Conversion (ADC):**
   - Configured with a **prescaler of 32** for a sampling rate of **38.46 kHz**.
2. **FFT Computation:**
   - Uses **64-point FFT** to transform audio signals into the frequency domain.
3. **LED Display Control:**
   - Displays amplitude variations across 32 frequency bands using column-wise mapping.
   - Modes toggle via a **push button**.

## Results
- Two circuit designs were simulated in **LTspice**, with Circuit 2 providing **better noise reduction**.
- The **full range sweep test** confirmed that frequencies up to **19 kHz** are accurately displayed.
- The logarithmic scale mode **enhanced low-frequency visualization**, making it more perceptually accurate.

## Future Work
- **Noise Monitoring System:** Log environmental noise levels categorized by frequency.
- **Audio Water Fountain:** Synchronize water jets with music using real-time signal processing.
- **Musical Instrument Tuner:** Visualize and tune instruments by observing harmonic frequencies.
- **Improved LED Display:** Upgrade to **RGB LED strips** for enhanced visual effects.
- **Higher Sampling Rate:** Use **faster microcontrollers** (ESP32) to improve resolution and accuracy.

## Installation & Usage
### Prerequisites
- **Arduino IDE** installed
- **ArduinoFFT and MD_MAX72xx libraries**

### Steps to Run the Project
1. Clone this repository:
   ```sh
   git clone https://github.com/yourusername/audio-spectrum-visualizer.git
   cd audio-spectrum-visualizer
   ```
2. Open the **Arduino sketch** in the **Arduino IDE**.
3. Connect the **Arduino Nano** to your PC and select the correct **COM Port & Board**.
4. Upload the code and power the circuit.
5. Play an audio source via an **AUX input**, and observe the **real-time frequency visualization**.

## References
- **32-Band Audio Spectrum Visualizer Analyzer** ([Project Hub](https://projecthub.arduino.cc/shajeeb/32-band-audio-spectrum-visualizer-analyzer-924af5))
- **Digital Signal Processing: Principles, Algorithms, and Applications** (J.G. Proakis, D.G. Manolakis)
- **Arduino FFT Audio Spectrum Analyzer on 8x32 LED Matrix** ([Maker Pro](https://maker.pro/arduino/projects/arduino-fft-audio-spectrum-analyzer-on-8x32-color-matrix-ws2812b))

## Contributors
- **Shruti Ramesh Hegde**  
- **Ashmita Das**  
