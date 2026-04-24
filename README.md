# Journey report

This repository hosts the journey report. The report is encrypted via
[staticrypt](https://github.com/robinmoisson/staticrypt) and requires a password
to be viewed. For the password, please contact 
`ilja (dot) wagner (at) bit (dot) team`.

The report is hosted as a GitHub page and can be viewed under 
[this URL](https://behaviouralinsights.github.io/journey-report/)

## Updating the report

The report can be updated by replacing the `index.html` file with an updated 
version. Note that the file has to be named `index.html`, otherwise the report 
link won't work. If the report is updated, the file needs to be re-encrypted; 
please ensure to re-use the existing password, otherwise the password needs to 
be reshared with all relevant parties. If the file is not re-encrypted, it will
be publicly viewable.

The GitHub page is auto-deployed on each push to the `main` branch.

## Encrypting the report
``` bash
# Install dependencies (adjust the command if not on MacOs)
brew install node

# Clone this repo
git clone https://github.com/BehaviouralInsights/journey-report.git
cd ./journey-report

# Update the report
mv ./path_to_new_report/new_report.html index.html

# Install staticrypt
npm install staticrypt

# Encrypt the report
staticrypt test.html -p <long-password>

# Replace the unencrypted with the encrypted report
# staticrypt dumps the encrypted report into the folder ./encrypted; 
# GitHub pages, however, expects the report to live in the root directory of the
# repository
mv ./encrypted/index.html index.html

# Push to GitHub
# The GitHub page will be auto-deployed after the push
git add .
git commit -m "chore: update report"
git push
```
