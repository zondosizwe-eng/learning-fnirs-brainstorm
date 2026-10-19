# Learning fNIRS with Brainstorm/NIRSTORM

This is a practical, screenshot-led route from raw fNIRS intensity to cortical HbO and HbR maps. The course follows a finger-tapping dataset through the Brainstorm graphical interface and its NIRSTORM extension. Each completed lesson identifies where to click, which input to select, the expected output and how to check the result.

!!! info "Course status — October 2026"
    Lessons **1–16 are complete**. Lessons **17–18 are coming later**, after the five-participant analysis has been completed and documented.

<div class="lesson-meta"><div><strong>Course author</strong><br>Sizwe Zondo</div><div><strong>Affiliation</strong><br>Department of Psychology, Rhodes University</div><div><strong>Level</strong><br>Beginner to intermediate</div></div>

## Who this course is for

The course is designed for honours, master's and doctoral students who are beginning task-based fNIRS analysis. It assumes basic familiarity with fNIRS terminology but does not assume previous Brainstorm or NIRSTORM experience.

## Course outcomes

By the end of the course, students should be able to:

1. Organise an fNIRS project in Brainstorm.
2. Explain the finger-tapping design and expected haemodynamic response.
3. Inspect raw intensity data and experimental events.
4. Screen channel quality and document exclusions.
5. Convert intensity to optical density, correct motion and estimate HbO/HbR.
6. Filter, epoch, reject trials and calculate a block average.
7. Construct an optical head model and interpret sensitivity outputs.
8. Reconstruct and display signed cortical haemoglobin responses.
9. Distinguish descriptive maps from inferential statistical evidence.

## The analysis pathway

**Raw intensity → ΔOD → TDDR → HbO/HbR → filter → epochs → average → optical model → cortical reconstruction**

Use the navigation above to begin with [Course orientation](getting-started.md) or go directly to [Lesson 1](lessons/lesson-01.md).

The course is an independent teaching adaptation of the [official Brainstorm/NIRSTORM tutorial](https://neuroimage.usc.edu/brainstorm/Tutorials/NIRSTORM). See [Acknowledgements and key publications](acknowledgements.md) for the original tutorial, the NIRSTORM software paper and the finger-tapping optical-tomography study underpinning the workflow.

!!! warning "Teaching and research use"
    The parameter choices in this course reproduce one tutorial dataset. They are not universal defaults for every instrument, participant group or study design. Before analysing research data, justify the quality thresholds, filtering, pathlength assumptions, epoch window and reconstruction settings for that dataset.

