
Certainly! Below is a concise README file that describes the purpose, solution, and implementation steps for the provided task:

Enforcing Branching Policy with Pre-receive Hook
Purpose
This repository contains a solution to enforce a branching policy where merges to the main branch are only allowed if there are open pull requests from at least two different branches (dev, staging, prod). This helps ensure that changes are reviewed and tested thoroughly before being merged into the main codebase.

Solution Overview
The solution involves implementing a pre-receive hook, a server-side Git hook that runs on the Git server before processing pushes. The hook checks for open pull requests from specified branches using the GitHub CLI (gh). If there are open pull requests from at least two different branches, the push to the main branch is allowed; otherwise, it is rejected.

Implementation Steps
Install GitHub CLI (gh):
Ensure that the GitHub CLI (gh) is installed on your system. You can download and install it from the official GitHub CLI repository: GitHub CLI.

Create the Pre-receive Hook Script:
Copy the provided pre-receive hook script into a new file named pre-receive, and make sure it has executable permissions:

bash
Copy code
chmod +x pre-receive
Place the Script in .git/hooks Directory:
Move the pre-receive script to the .git/hooks directory of your Git repository. This directory contains scripts that Git executes before and after certain operations such as commits and pushes.

Test the Hook:
Perform test pushes to the main branch and observe if the hook correctly allows or blocks the push based on the presence of open pull requests from at least two different branches (dev, staging, prod).

Adjustments:
If needed, adjust the script to fit your specific branching model or workflow. You can modify the list of branches or add additional conditions based on your requirements.

Documentation:
Document the presence of this hook for your team members. Add a brief description of the hook's purpose and functionality in your project's documentation or README file.
