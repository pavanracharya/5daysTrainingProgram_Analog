# 📅 Day 1 – CS Amplifier Analysis Using Cadence Virtuoso

## Objective
The objective of Day 1 was to gain hands-on experience in analog IC simulation by analyzing a basic Common Source (CS) amplifier using Cadence Virtuoso. The focus was on understanding device biasing, operating region, and small-signal behavior through DC, AC, transient, and parametric analyses.

---

## Tools Used
- Cadence Virtuoso (ADE L)
- Spectre Simulator

---

## Circuit Description
A Common Source NMOS amplifier was implemented and simulated. Proper DC biasing was applied to ensure the MOSFET operates in the saturation region. The circuit was analyzed under different simulation modes to study its performance and sensitivity to design parameters.

---

## 1. DC Analysis

DC analysis was performed to study the operating point of the circuit by sweeping the input bias voltage and observing the output voltage.

### Observations
- The NMOS transistor operates in the saturation region.
- Output voltage remains relatively stable for small variations in input bias.
- Operating point parameters such as drain current, VGS, VDS, and transconductance (gm) were verified.

### DC Response
![DC Analysis](DC analysis.png)

### DC Operating Point Parameters
![DC Operating Point](DC analysis_OP.png)

---

## 2. AC Analysis

AC analysis was carried out to evaluate the small-signal frequency response of the CS amplifier.

### Observations
- The circuit exhibits finite low-frequency gain.
- Gain decreases at higher frequencies due to parasitic capacitances.
- Phase response shows smooth transition, indicating stable operation.

### AC Magnitude and Phase Response
![AC Analysis](AC_ANALYSIS.png)

---

## 3. Transient Analysis

Transient analysis was performed by applying a sinusoidal input signal to the circuit and observing the time-domain response.

### Observations
- Output waveform follows the input signal with expected amplification.
- No clipping or distortion observed within the selected input amplitude range.
- Confirms correct biasing and linear operation.

### Transient Response
![Transient Analysis](transient_analysis.png)

---

## 4. Parametric Analysis

Parametric analysis was carried out by varying circuit parameters such as bias voltage and load resistance to study their effect on output voltage.

### Observations
- Output voltage decreases with increase in load resistance.
- Bias voltage significantly affects the operating point.
- Parametric sweep helps in understanding circuit sensitivity.

### Parametric Sweep Setup
![Parametric Analysis Setup](.parametric analysis.png)

### Parametric Output
![Parametric Output](parametric_output.png)

---

## Day 1 Summary
- Understood DC biasing and saturation region operation of NMOS.
- Learned DC, AC, transient, and parametric analysis using Cadence Virtuoso.
- Analyzed CS amplifier behavior in frequency and time domains.
- Established a strong foundation for analog IC design and layout considerations.

---
