# Plastic Tensile Testing Machine (PE & PVC)

A laboratory **tensile (traction) testing machine** I designed and built to characterise polyethylene (PE) and PVC samples: it pulls a specimen at a controlled speed, measures the force with a load cell, and plots the **stress / strain curve live** on a custom C# interface that also produces a PDF test report.

<p align="center">
  <img src="https://raw.githubusercontent.com/ayhem-b/Ayhem-portfolio/main/assets/images/tensile-rig-finished.jpg" alt="Finished tensile rig with its control box" height="300">
  <img src="https://raw.githubusercontent.com/ayhem-b/Ayhem-portfolio/main/assets/images/tensile-rig-frame-build.jpg" alt="Frame assembly in progress" height="300">
  <img src="https://raw.githubusercontent.com/ayhem-b/Ayhem-portfolio/main/assets/images/tensile-rig-schematic.jpg" alt="Control panel schematic" height="300">
</p>

## How it works

1. The specimen is clamped between two grips.
2. A **servo motor** drives the crosshead; a **Mitsubishi FX PLC** controls speed, limits and the test sequence.
3. A **load cell** measures the applied force; the PLC scales it linearly and exposes force and position in data registers.
4. The **C# WinForms HMI** (MX Component link) reads the registers in real time, draws elongation (%) vs stress (MPa), and exports a PDF report.
5. The test stops at specimen failure or at the configured limit.

## Main components

| Part | Role |
|---|---|
| Welded steel frame, two columns, crosshead | Structure, reaction forces |
| Servo motor + drive | Controlled displacement |
| Load cell + amplifier | Force measurement |
| Mitsubishi FX PLC | Sequence, limits, scaling |
| Control box (buttons, HMI PC link) | Operation |
| Clamps / grips | Specimen holding |

## Software

The HMI source (C#, .NET Framework 4.7.2, MX Component, iTextSharp) lives in a separate repository, **Stress-Machine**, which is private; access on request.

## Applications

Laboratory testing, material research, incoming quality control for plastic products.

## Status

Built and commissioned; the software is still being refined (report layout, additional test modes).

---
*Ayhem Belkhamsa — industrial automation engineer, Bizerte, Tunisia · [portfolio](https://ayhem-b.github.io/Ayhem-portfolio/)*
