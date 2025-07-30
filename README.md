# Simulation of the Coupling Between Plasmons and RF Photons in an LC Resonator

**Note:**  
This simulation uses the Green functions and density profiles generated in the repository:  
[erikawa-e/density_profile](https://github.com/erikawa-e/density_profile)  
Please use the code there to generate the necessary data.

Alternatively, you may use the files located in the following Google Drive folder:  
[Google Drive Folder](https://drive.google.com/drive/u/1/folders/1lC1xuzMQvBS7sev4N5r9cZi6F-KcE2N-)

Specifically, use the data in the following subfolders:
- `VibSweep`  
- `VmbSweep`  
- `VobSweep`  
- `GreenFunction`  

Depending on the sweep type, use the corresponding notebook:
- For VibSweep: [`Impedance_VibSweep.ipynb`](./Impedance_VibSweep.ipynb)
- For VmbSweep: [`Impedance_VmbSweep.ipynb`](./Impedance_VmbSweep.ipynb)
- For VobSweep: [`Impedance_VobSweep.ipynb`](./Impedance_VobSweep.ipynb)

---

## Vib Sweep

In `Impedance_VibSweep.ipynb`, we calculate the reflection coefficient when sweeping **Vib** from 15 V to 5 V while keeping **Vmb = Vob = -15 V** fixed.

For each value of Vib, we assume the electron number corresponds to the saturated number for that voltage configuration.

---

## Vmb Sweep

In `Impedance_VmbSweep.ipynb`, we calculate the reflection coefficient while sweeping **Vmb** from -32 V to 6.8 V, with **Vib = 10 V** and **Vob = -32 V** fixed.

For all Vmb values, we assume the number of electrons is equal to the saturated number at **Vib = 10 V**, **Vob = -32 V**, and **Vmb = -32 V**.

---

## Vob Sweep

In `Impedance_VobSweep.ipynb`, we calculate the reflection coefficient while sweeping **Vob** from 0 V to -160 V, with **Vib = Vmb = 17 V** fixed.

The saturated number of electrons as a function of Vob reaches a maximum at **Vob = -7.5 V**.  
This behavior is attributed to the vertical confinement of electrons floating **1 mm above the electrodes**. The electrode radii (4 mm, 5.7 mm, and 7 mm for inner, middle, and outer electrodes respectively) and the applied voltages (inner/middle = +17 V) result in an electric field configuration that provides optimal vertical confinement at this Vob, maximizing the electron density.

In the experiment, the sweep begins at **Vob = 0 V**. As Vob is decreased, one might expect the saturated number of electrons at Vob = 0 V to remain constant until a threshold, beyond which electrons are lost.  
However, experimental results agree best when we assume that **only 80% of the saturated number of electrons** at Vob = 0 V are initially present, and that electron loss begins from that point.  
The reflection coefficient in this notebook is computed under that assumption.

Such a reduction in electron number compared to the saturated value is often observed experimentally when the center voltage is high, the guard electrode is strongly negative, or the guard region is narrow.
