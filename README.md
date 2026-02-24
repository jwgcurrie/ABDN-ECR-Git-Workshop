# Experiment Workflow: A Quick Guide to Reproducible Research

This document outlines my recommended workflow for developing, reviewing, and versioning experiments using Git and GitHub. This process ensures that our research is transparent, reproducible, and collaborative.

## Core Git Concepts

Before being introduced to the workflow, let's define some key Git concepts:

* **Repository**: A repository is the central location for your project. It contains all of your project's files, folders, and the complete history of every change ever made to them. You work in a *local* repository on your computer, which is then synced with a *remote* repository hosted on GitHub (or other platforms).

    ```
    Project Folder (The Repository)
    ├── analysis/        (Your R/Python scripts)
    ├── stimuli/         (Images, audio, etc.)
    ├── README.md        (Instructions)
    └── .git/            (Hidden folder tracking all history)
    ```

*   **Branching**: A branch is an independent line of development. Creating a new branch allows you to work on a new prototype, feature or experiment without affecting the main codebase (the `main` branch).

    ```
    main branch:   o---o---o
                    \
    new branch:      \---o---o
    ```

*   **Committing**: A commit is a snapshot of your repository at a specific point in time, with a human readable label. Commits should be made **atomically**: frequent and represent a single logical change with a human readable label.

    ```
    new branch:    o---o---o---o
                   ^   ^   ^
                   |   |   |
    Commits        1   2   3
    ```

*   **Pushing and Pulling**: Pushing sends your committed changes to a remote repository, like GitHub. This backs up your work and (if desired) makes it available your collaborators or anyone on the internet. Pulling takes changes that are on the remote repository and applies them to your local copy.


    ```
    Local Repository      Remote Repository (GitHub)
      (Your Computer)

            o---o  --push-->   o---o
                               
            o---o  <--pull--   o---o
    ```

*   **Pull Request (PR)**: A pull request is a formal proposal to merge your changes from your branch into another branch (usually `main`). It allows for code review and discussion before the changes are integrated.

    ```
    main branch:   o---o---o-------o---o
                      \         /
    new branch:        o---o---o
    ```

*   **Release**: A release is a special type of commit. Essentially it is a version of your project that is intended for distribution. In our case, a release marks a version of the experiment that is ready for data collection.

    ```
    main branch:   o---o---o---o 
                               ^
                               |
                             Release! (2025.11_human-robot-audio)
    ```

## The Experiment Workflow

### 1. Begin: Create a New Repository

Start a new project by creating a new repository. Name the repository with a short and descriptive name, starting with 'exp' if an experiment (e.g., `exp-VPT-with-Robots`).

### 2. Branch: Isolate Your Work

Create a new branch for the specific experiment you are developing. Give it a descriptive name that reflects the experiment's purpose (e.g., `human-human-experiment`, `robot-interaction-stimuli`).

```bash
git checkout -b <branch-name>
```

### 3. Develop: Write and Test Your Experiment

Work on the experiment in your new branch. This includes writing the experiment code, preparing stimuli, and creating the analysis scripts.

*   **Commit Frequently**: Commit your progress with frequent, descriptive commits. A good commit message should be concise and explain the "why" behind the change.

    ```bash
    git commit -m "Add new stimuli for the human-robot condition"
    ```

*   **Push Regularly**: Regularly push your branch and its commits to the central GitHub repository.

    ```bash
    git push -u origin <branch-name>
    ```

### 4. Open a Pull Request (PR) for Review and Piloting

When the experiment is ready for an initial test, open a Pull Request to merge your branch into the `main` branch. In the PR description, clearly state that it is ready for pilot testing and provide instructions on how to run the experiment in the README. The repository should contain *everything* a person would need to recreated the experiment. 

### 5. Review and Pilot Testing

The review process has two parts:

*   **Code Review**: You, (or maybe a collaborator) will formally review the quality of the change introduced. They may add comments and suggestions to the PR.
*   **Pilot Test**: You will run the experiment with test participants, do vital data quality checks and collect feedback.

All feedback, bugs, and helpful suggestions from the pilot should be documented as comments on the Pull Request.

### 6. Iterate and Refine

Based on the feedback from the pilot, make the necessary changes by adding new commits to your branch. The Pull Request will automatically update with your changes. This cycle of piloting and refining can continue until the experiment is ready for data collection.

### 7. Merge and Release for Data Collection

Once the Pull Request has been approved and the piloting phase is finished, merge it into the `main` branch. Immediately after merging, create a formal Release from the `main` branch. The release should be tagged with a year and month with branch name (e.g., `2025.11_human-robot-audio`). This release is the definitive, pilot-approved version used for official data collection. Importantly, the release will be immutable, and you will not be able to make changes to the version of the experiment tagged by the release.

### 8. Follow-up Experiments

For follow-up studies or new conditions, repeat the workflow. Create a new branch from the up-to-date `main` branch and follow the steps for development, review, and release.


## Benefits of this Workflow

This workflow provides several benefits for our research:

*   **Reproducibility**: By versioning our experiments and analysis scripts, we can ensure that our research is reproducible. Anyone can download a specific release and run the exact same experiment and analysis.
*   **Collaboration**: The workflow facilitates collaboration by providing a clear process for developing and reviewing experiments.
*   **Transparency**: The entire history of the project is tracked in Git, making the research process transparent and auditable.
*   **Quality Control**: The code review and piloting process helps to identify and fix errors before data collection begins.

## Repository Privacy

To protect the intellectual property of our research, all experiment repositories should be private while the experiment is ongoing. Once the research is published, the repository should be made public to ensure transparency and align with open science principles.