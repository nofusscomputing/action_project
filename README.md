## No Fuss Computing - GH Action / Workflow for Project Issue/PR Triage

To use this reusable workflow add the following file to path `.github/workflows/project.yaml`

``` yaml

---

name: Project


on:
  issues:
    types:
      - opened
      - reopened
      - transferred
      - milestoned
      - demilestoned
      - closed
      - assigned
  pull_request: 
    types:
      - opened
      - reopened
      - closed



jobs:


  project:
    name: Project
    uses: nofusscomputing/action_project/.github/workflows/project.yaml@development
    with:
      PROJECT_URL: https://github.com/orgs/nofusscomputing/projects/7
    secrets:
      WORKFLOW_TOKEN: ${{ secrets.WORKFLOW_TOKEN }}


```
