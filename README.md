![conditioning](https://img.shields.io/badge/Signal%20Conditioning-white?style=for-the-badge&color=1591DC)
![LTSpice](https://img.shields.io/badge/LTSpice-white?style=for-the-badge&color=232F72)
![electronics](https://img.shields.io/badge/Electronics-white?style=for-the-badge&color=2F578A)
![latex report writing](https://img.shields.io/badge/LaTeX%20Report%20Writing-white?style=for-the-badge&color=2C5EAD)

# LTSpice Conditioning Circuit Design
Conducted in winter 2025 and in groups of two, this project involves designing a conditioning circuit to capture high-frequency tremors in a hypothetic robotic hand. Here is a section-by-section summary:
<p align="center">
  <img src="https://github.com/user-attachments/assets/c0c0b9f9-e86a-43bf-8658-3eaa9542ab2a"
       alt="ltcircuit"
       width="750"/>
   <br>
   <sub>Figure 1 — LTSpice Circuit Schematic</sub>
</p>


## 1. Component Selection

Focuses on selecting the primary hardware to capture high-frequency tremors (250–800 Hz) in a robotic hand control system. A **Murata 7BB-20-6 piezoelectric diaphragm** was selected as the transducer for its passive charge generation and high sensitivity. To prevent signal attenuation from this high-impedance source, a **TI LMP7721 op-amp** was chosen due to its ultra-low, femto-ampere input bias current.

## 2. Conditioning Circuit Design

Details the architecture and LTspice simulation of the multi-stage circuit, developed as a **simple replication** of a robotic hand control framework. The sensor is modeled via a **Butterworth-Van Dyke (BVD) circuit** to accurately replicate electromechanical behavior. The signal passes through a passive filtering network, including a 20 Hz high-pass, 1 kHz low-pass, and 50 Hz twin-T notch filter, before entering **two cascaded active differential amplifier stages** that provide a stable gain of over 100 each.

## 3. Potential Causes of Abnormal Behavior

Analyzes non-ideal real-world factors and outlines strategic hardware modifications to protect signal integrity. It addresses high-frequency EMI from motor drivers by proposing decoupling capacitors and an active low-pass buffer. It also counteracts thermal drift and sensor aging, which cause DC baseline shifts and signal clipping, by implementing an **active DC servo loop** and low-drift precision resistor networks.

## 4. Conclusion

Validates the complete front-end topology using LTspice simulation. The results confirm that a low-amplitude 13 mV input signal is successfully conditioned into a stable **3.3 V peak-to-peak output** without distortion or envelope drift, proving the design's viability for precise robotic motion-sensing applications.
