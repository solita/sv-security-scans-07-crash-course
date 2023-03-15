# 2023-03-15

## Explanations

1. Material prepared and used for Solita crash course on 2023-03-15

2. This repository contains sample Azure DevOps pipelines
   for a few security scans with a few extremely useful
   free open source tools:
   - `semgrep` (SAST)
   - `gitleaks` (secrets/credentials)
   - `tfsec` (IaC, Terraform)
   - `checkov` (IaC, Terraform, CloudFormation, K8s)
   - `trivy` (Docker images, SCA).
3. We do not have access to Public Azure DevOps repositories
   to publish contents of this repo.
   For that end we publish it as a subdirectory in a public
   **GitHub** repository. Just copy and modify pipelines in
   any of your Azure DevOps repos.


## SARIF: Static Analysis Results Interchange Format

How to read `.sarif` files with free open source tools.

1. Even though Semgrep and other security 
   tools are capable to generate `.sarif` files
   (https://sarifweb.azurewebsites.net/), which you can
   upload to GitHub and browse their nice representation there,
2. the action `github/codeql-action/upload-sarif@v2`
   required to upload `.sarif` files assumes that you have
   GHAS (GitHub Advanced Security license). This is a catch:
   Semgrep (no GHAS needed) generates a desired `.sarif`,
   but you cannot upload it to GitHub (requires GHAS).
3. To read `.sarif files` you may find useful Python
   command line tools https://github.com/microsoft/sarif-tools:

   ```
   # Install a virtual environment, if desired:
   python3 -m venv zvenv
   source zvenv/bin/activate
   pip install pip -U
   # Install sarif-tools
   pip install sarif-tools
   # See the summary in text form:
   sarif summary semgrep1.sarif
   # Generate a cvs file
   sarif csv -o semgrep1.csv semgrep1.sarif
   # Generate an html file
   sarif html -o semgrep1.html semgrep1.sarif
   ```


