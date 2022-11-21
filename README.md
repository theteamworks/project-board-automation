
# GitHub Project Board Automation

Edits to come, once the release notes have been updated.

An action that will automate the movement of the issues or pull requests on a GitHub projects(beta) board.

Before thinking of using this check out the following info and understand the assumptions made and the context it was designed for.

- The [Rationale](./docs/Rationale.md) for doing this
- The [Process](./docs/Rationale.md) the team should be following
- The [Detailed Workflow](./docs/Workflow.md) diagram of the action
- The [GitHub Settings](GitHubSettings.md) that are required
- The [Project Board](https://github.com/orgs/theteamworks/projects/3) will have columns as per this example (column names can be changed).

This has been done using GitHub Action `run` and GraphQL queries to be faster than building a full GitHub Action. This is because this action will run often and this action runs in 5-10 seconds.

## Setting up the action

This has been designed for a non-developer person to copy a file, configure a few settings and have the board automated. Obviously the team needs to understand and buy into the process, albeit a lightweight one.

### Copy the yaml file

Copy the GitHub Action [yaml file](https://github.com/theteamworks/project-board-automation/blob/main/.github/workflows/project_board_automation.yml) from this repository to get the latest version. Tagged versions with release notes and known issues will be created periodically. Copy this file into your repository in the same location `.github/workflows/`.

### Configure the action

The action requires a few organisation and project settings to be configured:

```yaml

# Configure the project specific variables
env:
  ORGANIZATION: theteamworks
  PROJECT_NUMBER: 3
  PR_URL: ${{ github.event.pull_request.html_url }}
  GITHUB_TOKEN: ${{ secrets.BOARD_AUTOMATION }}
  EXCLUDE_LABEL: 'no-issue'
  IN_PROGRESS_COLUMN_NAME: '"IN_PROGRESS"'
  REVIEW_REQUIRED_COLUMN_NAME: '"REVIEW_REQUIRED"'
  IN_REVIEW_COLUMN_NAME: '"IN_REVIEW"'
  APPROVED_COLUMN_NAME: '"APPROVED"'
  MERGED_COLUMN_NAME: '"MERGED"'
  DONE_COLUMN_NAME: '"DONE"'
  ITERATION_FIELD_NAME: Iteration   # See project settings (default is `Iteration`)

```

#### Exclusion label

In order for the action to know that the pull request does not require the mandate of a planned issue (as per the [no issue required](./docs/Process.md###pull-requests-with-no-issue-required) process) an exclusion label needs to be defined.

This label must be configured in the yaml file and also be present in each of the repositories that the work on the project board may come from.

## Dependabot

> ℹ️ Info: This action has not been fully working with dependabot pull requests and is the subject of further testing. Happy path has been tested.


```diff 
! Note: This action has not been fully working with dependabot pull requests and is the subject of further testing. Happy path has been tested.

```

$$\textcolor{orange}{\text{Note: This action has not been fully working with dependabot pull requests and is the subject of further testing. Happy path has been tested. }}$$

> ⚠️ Information:
```diff 
! Note: This action has not been fully working with dependabot pull requests and is the subject of further testing. Happy path has been tested.

```

