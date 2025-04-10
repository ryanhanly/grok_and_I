# Step 1: Directory Structure and GitHub Repo
## Directory Setup

1. Create the Base Structure:

   Open a terminal in WSL and navigate to your /code directory:
   ```
   cd /code
   mkdir tf_infra
   cd tf_infra
   ```
2. Create Stack 1 Directory:

   Inside `tf_infra`, create a subdirectory for the AWX stack:

   ```
   mkdir stack1-awx
   cd stack1-awx
   ```
3. Initial Files:
   Add the Terraform files from the "Stack 1: AWS-Hosted AWX" proposal. For now, create empty files:
   ```
   touch main.tf variables.tf outputs.tf
   ```
   Your structure should look like this:
   ```
   /code/
    └── tf_infra/
        └── stack1-awx/
            ├── main.tf
            ├── variables.tf
            └── outputs.tf
    ```
## GitHub Repository
1. Initialize Git: From /code/tf_infra:
   ```
    git init
   ```
2. Create a `.gitignore`: Add common Terraform and local files to ignore:
   ```
   echo -e "*.tfstate\n*.tfstate.backup\n.terraform/\nterraform.tfvars\n*.log" > .gitignore
   ```
3. First Commit:
   ```
   git add .
   git commit -m "Initial commit with stack1-awx structure"
   ```
4. Create GitHub Repo:
   - Go to GitHub and create a new repository (e.g., `tf_infra`)
   - Follow the instructions to link your local repo:
   ```
   git remote add origin https://github.com/<your-username>/tf_infra.git
   git branch -M main
   git push -u origin main
   ```
   Now your Terraform stacks are version-controlled in a GitHub repo under `/code/tf_infra`.

# Step 2: Virtual Environment
Using a virtual environment is a good DevOps practice when working with tools like Terraform, especially if you’re managing multiple projects or versions of dependencies (e.g., Terraform, AWS CLI, or Python-based tools for automation). Since Terraform itself doesn’t require a Python virtual environment, the benefit here would primarily apply if you’re using additional Python tools (e.g., for scripting, linting, or integrating with Ansible later). However, let’s set one up for completeness and future-proofing.

## Why Use a Virtual Environment?
**Isolation:** Ensures project-specific versions of Python packages (e.g., `awscli`, `boto3`) don’t conflict with system-wide installations.
**Reproducibility:** Makes it easier to share your setup with others via a `requirements.txt`.
**Good Practice:** Aligns with DevOps principles for managing dependencies.

## Setup Virtual Environment
1. Check Python Installation: Ensure Python is installed in WSL:
   ```
   python3 --version
   ```
   If not, install it: `sudo apt update && sudo apt install python3 python3-pip`.

2. **Create Virtual Environment:** From `/code/tf_infra`:
   ```
   python3 -m venv .venv
   ```

3. **Activate It:**
   ```
   source .venv/bin/activate
   ```
   Your prompt should now show (.venv).

4. **Install Useful Tools:** Optionally, install tools like awscli or terraform-docs (if you use Python-based helpers):
   ```
   pip install awscli
   ```
5. **Update**`.gitignore`: Add the virtual environment to `.gitignore`:
   ```
   echo ".venv/" >> .gitignore
   ```
6. **Deactivate:** When done: `deactivate`.