# DevSecOps Crash Course
### (This repo: sv-security-scans-07-crash-course)

Demo drop-in scans for Solita crash course 2023-03-15

## Remarks

1. This repo is made **public** for the participants' access convenience.
2. Note that unless you have GHAS (GitHub Advanced Security), 
   public GitHub repos have **more** security options 
   available, compared to internal and private repos.
   In particular, without GHAS:
   - internal and private repos have no possibility to use CodeQL SAST;
   - you cannot upload .sarif files with security scan results to GitHub;
   - you have no credentials scans.


## Workflows in `.github/workflows/`

### 1. `gitleaks-03.yml`

Uses the latest official Docker image from DockerHub for the
prominent credentials scan tool GitLeaks. Note that using 
an official GitHub action requires a license. Therefore, you are 
interested to adopt/adapt this workflow!


### 2. `tfsec-02.yml`

...


### 3. `checkov-03.yml`

...


### 4. `trivy-05-image`

...


### 5. `trivy-06-fs`

MISSING!


### 6. `pip-audit-02.yml`

...


### 7.
### 8.
### 9.
### 10.
### 11.
### 12.


### History

1. 2023-03-11 - started