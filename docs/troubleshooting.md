# Troubleshooting record

## Fluence mismatch encountered in Lesson 15

The initial head-model process requested four unavailable files: vertices `001589` and `006914` at both 685 and 830 nm.

### What was checked

- the wavelength-specific dOD input;
- default MRI and cortical surfaces;
- the remeshed head mask;
- the grey-matter-masked Voronoi interpolator;
- montage alignment;
- the supplied fluence directory.

### What not to do

Do **not** rename a nearby fluence file. Vertex identifiers refer to different spatial locations; renaming would silently create an invalid model.

### Resolution

The compatible fluences were obtained or generated on Windows, the head model was rerun, and the following outputs appeared for both wavelengths:

- Coverage
- Overlap measure
- Sensitivities
- Summed Sensitivities

<div class="figure-grid">
<figure><img src="../assets/images/head-model-settings.png" alt="NIRSTORM head model settings"><figcaption>Head-model settings used during the fluence import.</figcaption></figure>
<figure><img src="../assets/images/fluence-error.png" alt="Earlier missing fluence error"><figcaption>The earlier error is retained as a reproducible troubleshooting example.</figcaption></figure>
</div>

## General diagnostic sequence

1. Confirm the selected data domain.
2. Read the complete error rather than changing several settings at once.
3. Separate signal, event, anatomy, montage and software-version causes.
4. Change one justified parameter at a time.
5. Retain screenshots and document both unsuccessful and successful runs.

