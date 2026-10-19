# Analysis workflow and file lineage

| Stage | Input | Main operation | Output |
|---|---|---|---|
| Inspection | Raw intensity | Record display | Quality observations |
| Channel screening | Raw intensity | Detect bad channels | Accepted/rejected pairs |
| Optical conversion | Retained intensity | Raw to delta OD | Wavelength-specific dOD |
| Motion correction | dOD | TDDR | Corrected dOD |
| Haemoglobin conversion | Corrected dOD | MBLL | HbO, HbR and HbT |
| Temporal cleaning | Haemoglobin | IIR band-pass filter | Filtered Hb |
| Trial definition | Filtered Hb | Import around tapping/start | Task-locked epochs |
| Trial review | Epochs | Reject trial | Accepted epoch set |
| Response estimate | Accepted epochs | Average | AvgStderr response |
| Optical model | Wavelength dOD + anatomy | Fluence/head model | Sensitivity outputs |
| Reconstruction | dOD average + head model | wMNE | HbO/HbR cortical sources |

!!! important "Two connected branches"
    Signal preprocessing produces haemoglobin time series. Optical modelling uses wavelength-specific dOD, montage geometry, anatomy and fluences. These branches meet during cortical reconstruction.

## Core interpretation boundary

A sensitivity map describes where a channel is physically sensitive to absorption changes. A reconstructed HbO/HbR map estimates where the measured task response may originate. Neither is automatically a statistical significance map.

