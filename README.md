# Photocatalytic-MB-Degradation

---

## 🧩 Project Motivation

Methylene Blue is a persistent dye pollutant. To degrade it efficiently under visible light, this project develops a **hybrid catalyst** consisting of:

- 3D-printed PEGDA structures  
- Ni-doped pyrolytic carbon (conductive, porous)  
- Cu₂O semiconductor coating  
- Ag nanoparticles for plasmonic enhancement  

The structure increases **light absorption**, **charge separation**, and **reactive oxygen species (ROS)** formation.

---

## 🏗️ Fabrication Workflow

### **1. 3D Printing (DLP)**
- Resin: PEGDA  
- Ni doping: **0.5%, 1%, 5%, 10%** (by weight)  
- Layer thickness: **10 μm**  
- Exposure time: **5–15 s**  

### **2. Pyrolysis**
- Temperature: **900°C**  
- Atmosphere: **Ar/N₂**  
- Heating rate: **5–10°C/min**  
- Hold: **1–2 hours**  
- Output: **Ni-doped PyC scaffold**

### **3. Electrodeposition of Cu₂O + Ag**
- Electrolyte: CuSO₄·5H₂O (0.75%), NaOH (1.6%), Lactic acid (3.9%)  
- Voltage: **5 V**  
- Frequency: **50 Hz**, Duty cycle: **40%**  
- Time: **10–30 minutes**

---

## ☀️ Photocatalytic Experiment

### **Reaction Conditions**
- MB concentration: **10–20 ppm**  
- Light source: **Visible light (λ > 400 nm)**  
- Reaction time: **0–180 minutes**  
- Sampling interval: **30 minutes**  
- Monitoring: UV-Vis absorbance at **664 nm**

### **Kinetic Model**
Pseudo-first-order:
\[
\ln\left(\frac{C_0}{C}\right) = kt
\]

---

## ⚡ Photocatalytic Mechanism (Summary)

1. **Photon absorption:** Cu₂O generates e⁻/h⁺ pairs  
2. **Charge separation:**  
   - e⁻ transfer to Ag or PyC  
   - Ag produces hot electrons (plasmonic)  
3. **ROS generation:**  
   - e⁻ + O₂ → •O₂⁻  
   - •O₂⁻ → HO₂• → H₂O₂ → •OH  
4. **Dye degradation:** ROS and holes oxidize MB → CO₂ + H₂O

---

## 📊 Key Results

- **Ni-5%** exhibits the best photocatalytic activity  
- Cu₂O/Ag improves electron transfer and reduces recombination  
- MB degradation: **80–95% in 180 minutes**  
- Good fit to pseudo-first-order kinetics (R² > 0.95)

---

## 📈 Example Kinetic Fitting (Python)

```python
import numpy as np
import matplotlib.pyplot as plt

t = np.array([0, 30, 60, 90, 120, 150, 180])
C = np.array([...])  # input data
C0 = C[0]

k = np.polyfit(t, np.log(C0/C), 1)[0]

plt.plot(t, np.log(C0/C), marker='o')
plt.xlabel("Time (min)")
plt.ylabel("ln(C0/C)")
plt.title("Pseudo-First-Order Kinetics")
plt.show()
