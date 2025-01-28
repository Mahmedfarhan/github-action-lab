# GitHub-Action-Lab

This repository is for demonstrating GitHub Actions Workflow environment.

## Overview of the Project

In this lab assignment, the primary objective is to familiarize users with GutHub Actions by setting up a workflow that triggers on a specific event and executes predefined steps. Let us begin with the lab.

## How to Run This Project

1. Install Git

- To work with Git on your Windows machine, you'll need to install it OR you can use the Desktop or Web version of GitHub to work on the project.

2. Code Editor

-In order to edit code, download any software such as Visual Studio Code or any other txt editor tool which best suits.

3. A GitHub Repository

- Create a new private repository named `github-actions-lab`.
- Initialize with a `README.md` file.

4. Clone the Repository

- Copy the https or ssh URL from the repository and in your terminal in git Bash, type:

```bash
git clone https://github.com/username/github-action-lab.git

```
- Navigate into the cloned folder:

```bash
cd github-action-lab
```

5. Set Up a Workflow Directory

- Create `.github/workflows` directory within the repository.

```bash
mkdir .github/workflows
```
- This directory will store the `YAML` files defining the GitHub Actions workflows.


6. Create a Workflow File

- Now, create a `main.yml` file in the current working directory.

```bash
touch main.yml
```
- This file defines the workflow configuration including the event trigger and the tasks to be executed.
- Edit this file  using `nano` or `vim` editor tool, or any other software like VSCode.

7. Define Workflow Configuration

- This workflow will trigger upon push event to the `main` branch using `on:` keyword.
- This ensures that every time a commit is pushed to the `main` branch, the workflow automatically executes.

8. Add Workflow Steps

The Workflow consists of two key steps:
- **Checkout Repository Code:** This is done using `actions/checkout@v3`, which retrieved the repository's latest state.
- **Execute a Basic Command:** A command `echo "Hello, GitGub Actions!"` is run in the workflow environment to print a message in the logs.

9. Full Command for the workflow

```yml
#  Define a Simple Workflow with a Trigger

name: Simple GitHub Actions Workflow

on:
  push:
    branches:
      - main

# Add a Step to Check Out the Repository Code

jobs:
  say-hello:
    runs-on:  ubuntu-24.04
    steps:
      - name: Checkout Repository
        uses: actions/checkout@v3

# Add a Step to Run a Basic Message

      - name: Print a message
        run: echo "Hello, GitHub Actions!"
```

10. Commit and Push Changes

- The workflow file and related configurations are committed and pushed to the GitHub repository.
- Once it's pushed, this triggers the execution of the workflow.

11. Monitor the Workflow Execution

- The `Actions` tab in the GitHub repository is accessed to observe the workflow execution.
- Logs are available that van be reviewed to verify the successful or failure execution if the workflow steps.

## Expected Outcome

Upon successful execution, the workflow should print the message ` Hello, GitHub Actions! ` in teh logs.
And, the process demonstrats the ability to automate tasks using GitHub Actions and validates that the workflow triggers correctly on a push event.


## Conclusion

In this Project, we learned how set up and run a GitHub Actions workflow. This helped us see how workflows can automatically handle tasks like running commands, testing code, and managing deployments. It showed how automation can make development easier and more efficient.