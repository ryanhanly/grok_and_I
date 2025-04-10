Step 1: Directory Structure and GitHub Repo
Directory Setup

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