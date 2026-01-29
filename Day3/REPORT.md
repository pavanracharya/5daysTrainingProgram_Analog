# Day 3 – Bandgap Reference (BGR) & Differential Amplifier Analysis  
**Cadence Virtuoso | Spectre Simulator**

---

## Objective
The objective of Day 3 was to design and analyze a **Bandgap Reference (BGR)** and a **Differential Amplifier**, focusing on:
- Temperature-independent reference generation
- PTAT / CTAT behavior
- DC temperature sweep analysis
- Transient and frequency-domain (FFT) analysis
- Extraction of performance metrics such as **SINAD, SNR, ENOB, SFDR**

---

## Tools Used
- Cadence Virtuoso (ADE L / ADE XL)
- Spectre Simulator
- Visualization & Analysis XL (Calculator + Spectrum)

---

## 1. Bandgap Reference (BGR) Circuit

### BGR Schematic
![BGR Schematic](./images/BGR.png)

The BGR circuit combines:
- **PTAT voltage** (Proportional To Absolute Temperature)
- **CTAT voltage** (Complementary To Absolute Temperature)

to generate a near-constant reference voltage (~1.23 V).

---

## 2. DC Temperature Sweep Analysis (BGR)

### DC Response vs Temperature
![BGR DC Output](./images/BGR_op1.png)

### Observed Node Voltages
![BGR Nodes](./images/BGR_op2.png)

### Final Output Voltage
![BGR Output](./images/BGR_op3.png)

### Observations (from plots)
- **Temperature Range:** 0 °C to 100 °C
- **VOUT (Reference Voltage):**  
  ≈ **1.23 V** with slight negative slope
- **CTAT Voltage:** Decreases linearly with temperature
- **PTAT Voltage:** Increases linearly with temperature

---

## 3. PTAT Characteristic

### PTAT Voltage vs Temperature
![PTAT](./images/cdata.png)

### Extracted Values (from table)
| Temperature (°C) | PTAT Voltage (V) |
|------------------|------------------|
| 10               | 400.4 µV |
| 20               | 402.1 µV |
| 30               | 402.9 µV |
| 50               | 404.0 µV |
| 100              | 406.4 µV |

**PTAT Slope ≈ 0.4 mV / 100 °C**

---

## 4. Temperature Coefficient (Vref ppm)

### Vref ppm vs Temperature
![Vref ppm](./images/calc.png)

### Observations
- **Vref Temperature Coefficient:**  
  ≈ **−59 ppm/°C to −62 ppm/°C**
- Indicates reasonable temperature compensation but scope for trimming.

---

## 5. Differential Amplifier – Transient Analysis

### Differential Output Waveforms
![Differential Transient](./images/differential_transient.png)

### Observations
- Clean sinusoidal differential signals
- Proper common-mode operation
- No clipping observed in time domain

---

## 6. Frequency Domain (FFT) Analysis

### FFT of Differential Input
![FFT Din](./images/diff_spect1.png)

### FFT of Differential Output
![FFT Dout](./images/diff_spect2.png)

### Noise Spectrum
![FFT Noise](./images/diff_spect3.png)

---

## 7. FFT Performance Metrics (From m1–m4)

> **These values are taken directly from the bottom-right “Outputs” panel in the images**

### Input Node (Din1)
![Metrics Din1](./images/m1.png)

- **ENOB:** −1.8559 bits  
- **SINAD:** −9.4126 dB  
- **SNR:** −9.4126 dB  
- **SFDR:** 0.0895 dBc  

---

### Output Node (Dout) – Case 1
![Metrics Dout](./images/m2.png)

- **SINAD:** −6.1596 dB  
- **SNR:** −6.1596 dB  
- **SFDR:** 0.6834 dBc  
- **THD:** 0 %  

---

### Output Node (Dout) – Case 2
![Metrics Dout](./images/m3.png)

- **Signal Power:** −101.77 dB  
- **DC Power:** −58.37 dB  
- **Noise Floor:** −102.36 dB  
- **Integrated Noise:** −118.89 dB  

---

### Output Node (Dout) – Case 3
![Metrics Dout](./images/m4.png)

- **Signal Power:** −122.71 dB  
- **DC Power:** −28.70 dB  
- **Noise Floor:** −126.55 dB  
- **Integrated Noise:** −143.09 dB  

---

## 8. Key Learnings

- Bandgap reference achieves **~1.23 V** with controlled temperature variation.
- PTAT and CTAT components correctly cancel temperature dependence.
- Differential amplifier shows stable transient behavior.
- FFT analysis highlights **noise-dominated performance**, indicating:
  - Low signal amplitude
  - Scope for gain optimization
  - Need for better biasing and filtering

---

## Day 3 Summary
- Designed and analyzed a **Bandgap Reference circuit**
- Verified **PTAT, CTAT, and temperature compensation**
- Performed **DC temperature sweep**
- Analyzed **Differential Amplifier in time and frequency domains**
- Extracted **ENOB, SINAD, SNR, SFDR, Noise Power** directly from simulation

---


