# Lesson 16 — Cortical reconstruction and signed HbO/HbR maps

<div class="lesson-meta"><div><strong>Status</strong><br>Complete</div><div><strong>Input</strong><br>Averaged dOD + NIRS head model</div><div><strong>Output</strong><br>HbO/HbR/HbT cortical sources</div></div>

## Aim

Use weighted minimum-norm estimation (wMNE) to reconstruct the averaged tapping response on cortex, inspect the right-hand motor scout, and create signed HbO and HbR maps at 12.20 s.

## Critical file choice

!!! warning
    Use the **averaged, filtered dOD** result in the same data branch as the **NIRS head model**. Do not use the channel-level MBLL Hb average for this source-reconstruction process.

### 1. Open the reconstruction process

1. Select the appropriate averaged dOD result.
2. Place it in **Files to process**.
3. Click **Run**.
4. Open **NIRS → Sources → 3D reconstruction - wMNE**.

![Menu route to wMNE reconstruction](../assets/lesson16-reconstruction-menu.png)

### 2. If needed, recreate the dOD epochs and average

Our first attempt revealed that the available average was from the Hb branch. We returned to the filtered dOD recording, imported `tapping/start` epochs from −10 to +30 s with the −10 to 0 s baseline, rejected the known bad first trial, and averaged the 19 accepted dOD epochs.

![Import window for the dOD reconstruction branch](../assets/lesson16-import-window.png)

The correct dOD average and NIRS head model must be visible together in the relevant condition/run branch.

![Correct reconstruction inputs in the database tree](../assets/lesson16-correct-inputs.png)

### 3. Enter the wMNE settings

| Setting | Value used |
|---|---|
| Method | Weighted minimum-norm estimate |
| Field of view | 5.00 cm |
| Depth weighting factor | 0.3 |
| Reconstruction window | −10.00 to +30.00 s |
| Compute baseline noise covariance | Selected |
| Baseline window | −10.00 to −0.10 s |
| Outputs | dOD, HbO, HbR and HbT |

![Final wMNE settings](../assets/lesson16-final-wmne-settings.png)

Click **Run**. Brainstorm creates wavelength and chromophore source results.

![Cortical source result after reconstruction](../assets/lesson16-source-result.png)

## Inspect the right-hand motor scout

### 4. Open a chromophore source result

1. Open **MNE sources | HbO** or **MNE sources | HbR**.
2. Display the cortex from the top or a useful lateral view.
3. In the **Scout** tab, select the hand-motor scout (RC hand in this dataset).
4. Keep **Values: Relative**.

<div class="figure-grid">
<figure><img src="../assets/lesson16-result-menu.png" alt="Source result display menu"><figcaption>Open the source result and its display controls.</figcaption></figure>
<figure><img src="../assets/lesson16-scout-map.png" alt="Right hand scout on cortex"><figcaption>The red outline is an anatomical scout, not significance.</figcaption></figure>
</div>

### 5. Plot the scout time course

Click the graph icon immediately to the left of **Atlas**. To compare HbO and HbR, open both result files and select **Overlay: Files**.

<div class="figure-grid">
<figure><img src="../assets/lesson16-overlay-view.png" alt="Overlaying source results"><figcaption>Overlay the chromophore result files.</figcaption></figure>
<figure><img src="../assets/lesson16-scout-timecourse.png" alt="Scout time course"><figcaption>Task-locked scout response across −10 to +30 s.</figcaption></figure>
</div>

In our descriptive example, HbO rose and HbR decreased around the expected post-onset period. This is a single-participant demonstration, not a significance test.

## Create the tutorial-style maps at 12.20 s

### 6. Set the exact time

1. Open the HbO source map.
2. Enter **12.20** in the current-time field and press **Enter**.
3. Confirm that the red time cursor moves to 12.20 s.

<div class="figure-grid">
<figure><img src="../assets/lesson16-time-field.png" alt="Current time field"><figcaption>Locate the current-time control.</figcaption></figure>
<figure><img src="../assets/lesson16-time-1220.png" alt="Map at 12.20 seconds"><figcaption>Confirm the map is evaluated at 12.20 s.</figcaption></figure>
</div>

### 7. Make the map signed and visible

Repeat these steps for HbO and HbR:

1. Open **Surface → Data options** and set **Amplitude = 0%**.
2. Open **Colormaps → Sources**.
3. Clear **Absolute values**; accept the warning to display relative/signed values.
4. Select **Range → [-max,max]**.
5. Keep **Maximum → Global**.
6. Select **Colormap → Rainbow → jet**.
7. Keep the RC hand scout outline visible.

<div class="figure-grid">
<figure><img src="../assets/lesson16-display-options.png" alt="Source display options"><figcaption>Set amplitude and signed display options.</figcaption></figure>
<figure><img src="../assets/lesson16-signed-map.png" alt="Signed cortical map"><figcaption>Signed colour scale preserves increases and decreases.</figcaption></figure>
</div>

### 8. Save the HbO and HbR figures

<div class="figure-grid">
<figure><img src="../assets/lesson16-hbo-signed-map.png" alt="HbO cortical map at 12.20 seconds"><figcaption><strong>HbO:</strong> positive red/yellow response near the hand scout.</figcaption></figure>
<figure><img src="../assets/lesson16-hbr-signed-map.png" alt="HbR cortical map at 12.20 seconds"><figcaption><strong>HbR:</strong> negative blue/purple response in a similar region.</figcaption></figure>
</div>

The tutorial comparison views below helped define the desired signed-map appearance.

<div class="figure-grid">
<figure><img src="../assets/lesson16-hbo-tutorial-view.png" alt="Tutorial style HbO view"><figcaption>Tutorial-style HbO target.</figcaption></figure>
<figure><img src="../assets/lesson16-hbr-tutorial-view.png" alt="Tutorial style HbR view"><figcaption>Tutorial-style HbR target.</figcaption></figure>
</div>

## Interpretation boundaries

- The scout outline is an anatomical ROI, not significant activation.
- The maps are descriptive single-participant reconstructions.
- HbO and HbR may use separate global scales, so colour intensity is not directly comparable.
- Clearing **Absolute values** is essential for distinguishing positive HbO from negative HbR.

## Checkpoint

- The dOD average and head model are in the same analysis branch.
- wMNE used the recorded field-of-view, depth, reconstruction and baseline settings.
- HbO/HbR/HbT source results exist.
- Signed HbO and HbR maps were displayed at 12.20 s.

## Troubleshooting

| Problem | Check |
|---|---|
| “Head model not found” | Use the averaged dOD result in the branch containing the NIRS head model. |
| Process rejects Hb data | Recreate epochs and the average from filtered dOD, not MBLL Hb. |
| HbR appears only positive | Clear **Absolute values** and use the symmetric `[-max,max]` range. |
| Scout outline is mistaken for activation | The outline defines an anatomical ROI only. |

## Self-check {.quiz}

**1. Which average enters cortical reconstruction?**  
A. Averaged filtered dOD  
B. Channel-level Hb average  
C. Raw intensity

<details><summary>Reveal answer after attempting</summary><strong>A.</strong> The wMNE branch uses the dOD average together with the NIRS head model.</details>

**2. What reconstruction window was used?**  
A. −10 to +30 s  
B. 0 to 1 s  
C. 300 to 570 s

<details><summary>Reveal answer after attempting</summary><strong>A.</strong> It matches the event-locked epoch interval.</details>

**3. Why clear Absolute values?**  
A. To preserve positive and negative source signs  
B. To remove the scout  
C. To change sampling rate

<details><summary>Reveal answer after attempting</summary><strong>A.</strong> Absolute values would hide the distinction between increases and decreases.</details>

**4. What does the red scout outline represent?**  
A. An anatomical region of interest  
B. A significance threshold  
C. A bad channel

<details><summary>Reveal answer after attempting</summary><strong>A.</strong> The outline identifies the hand-motor scout.</details>

**5. Which descriptive pattern was observed near the hand scout?**  
A. HbO increase with HbR decrease  
B. Both signals perfectly flat  
C. HbO decrease with HbR increase only

<details><summary>Reveal answer after attempting</summary><strong>A.</strong> The example shows the expected complementary haemodynamic pattern.</details>
