# Publishing this course with Read the Docs

The course is already configured for Read the Docs. Publication has two stages: place the project in a Git repository, then import that repository into Read the Docs.

## Before publication

1. Review the course locally with `mkdocs serve`.
2. Complete the **Publication-readiness checklist**.
3. Decide whether the repository and documentation should be public or private.
4. Replace or remove any teaching screenshots that contain information you do not want published.

## Stage 1 — Create the Git repository

1. Sign in to GitHub, GitLab or Bitbucket.
2. Create a repository for the course, for example `learning-fnirs-brainstorm`.
3. Upload the **contents** of this folder so that `mkdocs.yml` and `.readthedocs.yaml` are at the repository root.
4. Commit and push the files.

Do not upload only the generated `site/` directory. Read the Docs needs the Markdown source, images and configuration files.

## Stage 2 — Import into Read the Docs

1. Sign in to [Read the Docs](https://readthedocs.org/).
2. Connect the Git provider that contains the course repository.
3. Select **Import a Project** and choose the course repository.
4. Confirm the project name and repository URL.
5. Start the first build.
6. Open **Builds** and check that the build completes successfully.
7. Open the generated documentation URL and test the navigation, figures, search and answer panels.

Read the Docs will use `.readthedocs.yaml` to select Python 3.12, install the packages in `requirements.txt` and build `mkdocs.yml`.

## Updating the published course

Edit the Markdown or image files, commit the changes and push them to the repository. Read the Docs will rebuild the website from the updated source.

## First-build checks

- The home page opens without a 404 error.
- All 18 lesson titles appear in the navigation.
- Figures load across Lessons 1–16.
- The light/dark theme control works.
- Search finds `TDDR`, `fluence`, `HbO` and `wMNE`.
- MCQ answers stay hidden until the learner opens them.
- Lessons 17–18 are visibly labelled **Coming later**.

## If a build fails

Open the failed build in Read the Docs and inspect its log. First check:

1. `.readthedocs.yaml` is at the repository root and has that exact filename.
2. `mkdocs.yml` is also at the repository root.
3. `requirements.txt` exists.
4. File and image paths match their capitalisation exactly.
5. The repository contains the `docs/` directory and its assets.
