# Solita DevSecOps Crash Course, 2023-03-15
### (This repo name: `solita/sv-security-scans-07-crash-course`)


## Remarks

1. This repo is made **public** for the participants' access convenience.
2. Note that unless you have GHAS (GitHub Advanced Security), 
   public GitHub repos have **more** security options 
   available, compared to internal and private repos.
   In particular, without GHAS:
   - internal and private repos have no possibility to use CodeQL SAST;
   - you cannot upload .sarif files with security scan results to GitHub;
   - you have no credentials scans.
3. There is also a `.pptx` file with the presentation slides.
4. There are also a few recent DevSecOps reports about 
   current statistics about security vulnerabilities.
5. Finally, there is a subdirectory `Azure-DevOps-security-pipelines/`
   containing Azure DevOps pipelines with the magnificent security
   scan tools we discussed in the meeting. Compare how same things 
   are expressed in GitHub Actions and Azure DevOps pipelines.


## Workflows in `.github/workflows/`

### 1. `gitleaks-03.yml`

Uses the latest official Docker image from DockerHub for the
prominent credentials scan tool GitLeaks. Note that using 
an official GitHub action requires a license. Therefore, you are 
interested to adopt/adapt this workflow to be able to use Gitleaks!


### 2. `tfsec-02.yml`

Terraform IaC security scanner.


### 3. `checkov-03.yml`

IaC security scanner (Terraform, CloudFormation, k8s)


### 4. `trivy-05-image`

Prominent Docker container scanner


### 5. `trivy-06-fs`

MISSING!


### 6. `pip-audit-02.yml` (SCA, dependencies)

Scans for security vulnerabilities in Python virtual environments 
installed using `pip install -r requiremets.txt`

There are low security vulnerabilities with
```
aws-encryption-sdk==2.0.0
```

but they are eliminated with
```
aws-encryption-sdk==2.3.0
```

Changing package versions is done in the requirements file 
`requirements-pip-audit-02.txt`.


### 7. `eslint-02.yml`

Does not work. REMOVE??? Remove `package.json` as well!


### 8. `ci-...-aws-enc-02.yml`

Here we illustrate another option: you do not need to keep your code 
in the same repository as your workflows... 
Tested on AWS Encryption library


### 9. `ci-...-py-alg-02.yml`

Same, tested on Python Algorithms library.


### 10.
### 11.
### 12.


### History

1. 2023-03-11 - started