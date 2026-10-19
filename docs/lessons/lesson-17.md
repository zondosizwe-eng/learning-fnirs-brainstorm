# Lesson 17 — Five-participant Brainstorm replication

<div class="lesson-meta"><div><strong>Status</strong><br>Coming later</div><div><strong>Dataset</strong><br>NEMAR nm000175</div><div><strong>Participants</strong><br>Five</div></div>

!!! info "Why this lesson is not yet complete"
    This page will become a screenshot-led procedure only after the five recordings have been processed in Brainstorm/NIRSTORM. Keeping it as a planning page prevents untested steps or assumed outputs from being presented as completed instruction.

## Aim

Repeat the complete Brainstorm/NIRSTORM pipeline for five finger-tapping participants using consistent, documented decisions.

## Planned workflow

1. Download the selected participants from [NEMAR dataset nm000175](https://nemar.org/dataset/nm000175).
2. Create a dedicated multi-participant Brainstorm protocol.
3. Import each SNIRF recording, participant metadata, events and montage.
4. Apply a common channel-quality framework while documenting participant-specific exclusions.
5. Convert intensity to dOD and apply TDDR.
6. Convert to HbO/HbR for the channel-level pathway and apply the common filter.
7. Create `tapping/start` events and comparable epochs.
8. Review trials, document rejections and calculate participant averages.
9. Construct or reuse anatomically compatible optical models.
10. Generate comparable RC hand time courses and cortical maps.

## Processing log to retain

| Item | Record for every participant |
|---|---|
| Raw duration and sampling | Confirmed value |
| Events | Number and timing of tapping blocks |
| Bad channels | Source–detector pairs and reason |
| Motion correction | Process and visual check |
| Filter | Identical specification |
| Epochs | Window and accepted trial count |
| Anatomy | Individual or common template |
| Reconstruction | Identical wMNE settings |

!!! note
    This page is intentionally a structured placeholder. It will be expanded when the five recordings are processed.

## Preview questions {.quiz}

**1. Why retain a participant-level processing log?**  
A. To make exclusions and parameter differences transparent  
B. To avoid looking at the data  
C. To replace the Brainstorm database

<details><summary>Reveal answer after attempting</summary><strong>A.</strong> Group analysis requires traceable participant-level decisions.</details>

**2. Which feature should be consistent across participants?**  
A. The intended preprocessing and outcome definitions  
B. The number of artefacts  
C. Every raw signal amplitude

<details><summary>Reveal answer after attempting</summary><strong>A.</strong> Comparable methods and outcomes are essential; raw quality can legitimately differ.</details>

