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
