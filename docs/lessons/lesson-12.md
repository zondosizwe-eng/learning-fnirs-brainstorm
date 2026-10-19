# Lesson 12 — Band-pass filtering

<div class="lesson-meta"><div><strong>Status</strong><br>Complete</div><div><strong>Input</strong><br>TDDR-corrected Hb [Topo]</div><div><strong>Output</strong><br>IIR-band Hb</div></div>

## Aim

Reduce slow drift and faster physiological fluctuations while retaining the slower task-related haemodynamic response.

## File lineage

> **Lesson 11:** corrected dOD → MBLL → Hb [Topo].  
> **Lesson 12:** select that Hb derivative → IIR band-pass filter → filtered Hb.

### 1. Select the Lesson 11 output

Select **Hb [Topo]** beneath the TDDR-corrected branch and drag it to **Files to process**. Do not return to raw intensity or uncorrected OD.

![Hb input selected for filtering](../assets/lesson12-input-hb.png)

### 2. Open the IIR band-pass filter

1. Click **Run**.
2. Open **NIRS → Pre-process**.
3. Select the **IIR band-pass filter** in the Brainstorm 2026 interface.

![Band-pass filter menu route](../assets/lesson12-filter-menu.png)

### 3. Enter the training settings

| Setting | Value |
|---|---|
| High-pass edge | 0.01 Hz |
| Low-pass edge | 0.10 Hz |
| Filter type | IIR/Butterworth, zero-phase as displayed |
| Filter order | 3 |
| Keep mean | Selected |

![IIR band-pass settings](../assets/lesson12-filter-settings.png)

These are teaching settings for this dataset, not universal defaults. A study should justify its passband before inspecting outcomes.

### 4. View the response before running

Click **View filter response**. Confirm that the passband lies between 0.01 and 0.10 Hz and that the properties match the intended process. Close the response window, then click **Run**.

![Filter response and properties](../assets/lesson12-filter-response.png)

### 5. Find the output—not the input

A new branch labelled **IIR-band** should appear. Expand it and select its Hb output.

<div class="figure-grid">
<figure><img src="../assets/lesson12-output-folder.png" alt="IIR band output folder"><figcaption>The new filtered branch.</figcaption></figure>
<figure><img src="../assets/lesson12-output-tree.png" alt="Filtered Hb selected in tree"><figcaption>Select the derivative inside IIR-band.</figcaption></figure>
</div>

### 6. Compare filtered and unfiltered data

Open both versions with the same time window and scale. Filtering should reduce slow baseline wander and high-frequency variation without erasing the slower haemodynamic structure.

<div class="figure-grid">
<figure><img src="../assets/lesson12-unfiltered-display.png" alt="Unfiltered haemoglobin display"><figcaption>Before band-pass filtering.</figcaption></figure>
<figure><img src="../assets/lesson12-filtered-display.png" alt="Filtered haemoglobin display"><figcaption>After band-pass filtering.</figcaption></figure>
</div>

## Important cautions

- Filtering cannot rescue a saturated or uncoupled channel.
- Aggressive filtering can distort response timing and amplitude.
- Edge transients may occur near the start and end; inspect the first epoch carefully.

## Checkpoint

- The input was TDDR-corrected Hb.
- The exercise passband was 0.01–0.10 Hz.
- The output was opened from the **IIR-band** branch.

## Troubleshooting

| Problem | Check |
|---|---|
| No filtered output appears | Confirm the Hb file was in Files to process and Run completed. |
| Display looks unchanged | Verify that you opened the derivative under IIR-band. |
| Large distortion at the beginning | Treat it as a possible edge effect and inspect the first epoch. |

## Self-check {.quiz}

**1. Which file entered the filter?**  
A. TDDR-corrected Hb [Topo]  
B. MRI T1  
C. Original intensity only

<details><summary>Reveal answer after attempting</summary><strong>A.</strong> The lesson filters the haemoglobin derivative produced by MBLL.</details>

**2. What passband was used?**  
A. 0.01–0.10 Hz  
B. 1–40 Hz  
C. 100–200 Hz

<details><summary>Reveal answer after attempting</summary><strong>A.</strong> This retains slow fNIRS task-related variation while attenuating slower drift and faster noise.</details>

**3. Why view the filter response?**  
A. To verify the numerical specification  
B. To create events  
C. To register MRI

<details><summary>Reveal answer after attempting</summary><strong>A.</strong> It checks that the intended frequency band is retained.</details>

**4. Where is the result found?**  
A. In the new IIR-band branch  
B. Under MRI only  
C. In the scout atlas

<details><summary>Reveal answer after attempting</summary><strong>A.</strong> Brainstorm preserves the input and creates a filtered derivative.</details>

**5. Why inspect the beginning of the filtered recording?**  
A. Filter-edge transients can appear there  
B. HbO is never present there  
C. It changes participant age

<details><summary>Reveal answer after attempting</summary><strong>A.</strong> Edge effects may contaminate an early epoch.</details>
