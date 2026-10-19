# Publication-readiness checklist

Use this page while reviewing the course before publication. It separates content decisions from technical publication checks.

## Course-level checks

- [ ] The course title and author details are correct.
- [ ] The intended student level is clear.
- [ ] Lessons 1–16 reflect the workflow actually completed.
- [ ] Lessons 17–18 are clearly identified as future work.
- [ ] Every completed lesson has an aim, an input/output pathway, a checkpoint and five MCQs.
- [ ] The distinction between template-based and participant-specific anatomy is clear.
- [ ] Descriptive cortical maps are not described as statistical significance maps.
- [ ] The official tutorial, NIRSTORM paper, workflow paper and Brainstorm paper are acknowledged accurately.
- [ ] Public use of tutorial-data-derived screenshots is consistent with the dataset conditions or has been clarified with the tutorial authors.

## Parameters to verify against Brainstorm records

- [ ] Finger-tapping block count, duration and sampling rate in Lesson 2.
- [ ] Bad-channel criteria and channel decisions in Lesson 8.
- [ ] Band-pass filter settings in Lesson 12.
- [ ] Epoch interval and baseline choices in Lesson 13.
- [ ] Fluence/head-model settings in Lesson 15.
- [ ] wMNE and noise-covariance settings in Lesson 16.

## Figure checks

- [ ] Screenshots are legible on a laptop display.
- [ ] No screenshot contains information that should remain private.
- [ ] Captions explain what each figure demonstrates.
- [ ] Every instructional screenshot appears immediately after the step it supports.
- [ ] Screenshot text remains readable on a typical laptop display or after enlargement.
- [ ] Alternative text identifies the purpose of every instructional image.
- [ ] HbO and HbR maps show the intended 12.20-second view.
- [ ] The RC hand outline is explained as an anatomical scout.

## Student experience

- [ ] Instructions identify the relevant Brainstorm tab or panel.
- [ ] Each processing step names the input selected and the output expected.
- [ ] Technical terms are introduced before they are assessed.
- [ ] MCQ answers remain hidden until opened.
- [ ] Troubleshooting advice distinguishes safe corrections from invalid shortcuts.

## Publication checks

- [ ] The project builds locally with `mkdocs build --strict`.
- [ ] All internal links and images work.
- [ ] `.readthedocs.yaml` and `mkdocs.yml` are at the repository root.
- [ ] The first Read the Docs build succeeds.
- [ ] The published URL works without requiring a ChatGPT account.
