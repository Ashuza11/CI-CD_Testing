# 02_06 Challenge: Develop a CI Workflow

## REQUIREMENTS

Help the team set up a continuous integration pipeline using a GitHub Actions starter workflow.

Start by creating a new repo and adding the exercise files for this challenge.

requirements.txt
test_pandas_version.py
Use the GitHub Actions web interface to create a starter workflow.

Run the workflow and observe the problems the team is referring to.

Fix any errors in the code so that the tests pass successfully.

Update the workflow to add a summary of the tests being run.

Update the workflow so that it has permissions to create checks in the Actions interface.

Update the call to pytest so that it creates a JUnit report named junit.xml.

python -m pytest --verbose --junit-xml=junit.xml
Add a new step that uses the JUnit Report Action from the GitHub Marketplace:

```- name: Publish Test Report
  uses: mikepenz/action-junit-report@v3
  if: success() || failure() # always run even if the previous step fails
  with:
  report_paths: '\*\*/junit.xml'
  detailed_summary: true
  include_passed: true
```
