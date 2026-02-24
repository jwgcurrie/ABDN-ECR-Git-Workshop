# experiment-workflow-workshop 

Welcome to the ECR workshop on git/github. We are using this repo to practice working together on a collaborative experiment!

The goal of this session is to understand core git concepts, and practice the **Experiment Workflow**. By the end of this session, you will know how to safely contribute to a shared project.

## Task:

Your task is to "check in" to the workshop by adding a file. 
Steps:

### 1. Branching
**Rule:** When collaborating, *never* work directly on the `main` branch.

1.  Open GitHub Desktop.
2.  Make sure your Current Branch is set to **main**.
3.  Click **New Branch**.
4.  **Name it:** `yourname/check-in` (e.g., `joel/check-in`).

### 2. The Work
1.  Open the repository folder on your computer.
2.  Navigate to the `task/` folder.
3.  Edit the `list.md` file, and add your name.
4.  Save the file.

### 3. Commit and Push
1.  Return to GitHub Desktop. You should see your new file listed in the changes.
2.  **Commit** your changes: Write a summary (e.g., "Add Joel to list") and click **Commit**.
3.  **Push** your branch: Click the **Push origin** (or Publish branch) button to send your branch to GitHub.

### 4. Pull Request
1.  Click **Create Pull Request** in GitHub Desktop. This will open your web browser.
2.  Review the title and description.
3.  Click **Create pull request**.
4.  **STOP:** Wait for a colleague or the host to review your PR.

---

## Key Concepts

* **Main Branch:** This code is stable.
* **Branch:** Your sandbox. It is an isolated copy of the code where you can experiment safely.
* **Pull Request (PR):** A proposal to change the main branch. This is where we review work before it becomes permanent.

---

## Phase 2: The Release

Once everyone's Pull Request has been reviewed and merged into `main`, the experiment (or in this case, our team list) is considered **stable**.

To mark this milestone, the maintainer will create a **Release** on GitHub.

### Why do we release?
* **Immutability:** A release tags a specific moment in the project's history. Even if we change the code tomorrow, we can always download the `v1.0` zip file and get exactly what we have right now.
* **Reproducibility:** When you publish a paper, you can cite the specific **Release Version** used to collect data.

### Your Final Step
Once the release is created by the host:

1.  Switch your branch back to **`main`** in GitHub Desktop.
2.  Click **Fetch origin**.
3.  Click **Pull origin**.
4.  Open the `task/` folder on your computer—you should now see everyone's files together!