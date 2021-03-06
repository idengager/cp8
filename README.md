# CP-8 Cookpad Bot

[![Deploy](https://www.herokucdn.com/deploy/button.svg)](https://heroku.com/deploy)

<img src="https://cloud.githubusercontent.com/assets/104138/13375017/617ffdd0-dd95-11e5-9b59-87605963b351.png" width="40%"/>

## Purpose

- Keep trackers clean by cleaning out stale pull requests/issues
- Help reviewers focus by tagging WIP pull requests
- Tighten review loop by notifying when PRs need immediate attention

## Usage

CP-8 can:

- Close issues with no activity
- Add a `WIP` label to PRs with "[WIP]" in title
- Notify in specified Slack channel when:
  - a new (non-WIP) PR is opened
  - a WIP PR is "un-WIPped"
  - a `:recycle:` comment is posted
  - a PR is approved/has changes requested
- Automatically add new issues to projects
- Move issues to other repos

## Setup

- Invite GitHub bot user to GitHub repo
- Add `/payload` webhook to GitHub repo

## Configuration

```ruby
/payload?config[stale_issue_weeks]=6 # Set stale issue cutoff to 6 weeks
/payload?config[review_channel]=reviews # Send review requests/updates to specified Slack channel
/payload?config[project_column_id]=49 # Automatically add new issues to a project column
/payload?config[move_to_prefix]=move-to # Move issue to other repo when labeled with prefix, ie `move-to:cookpad/cp8`
```
