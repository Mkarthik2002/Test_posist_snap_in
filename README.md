Connect GitHub with DevRev, and ensure your work stays in sync between the two systems, such that issues and statuses are always real-time and driven by code activity. GitHub for DevRev is a snap-in that has been used by several organizations, and ties DevRev issues closely with GitHub activity, eliminating the need for humans to manage issues.

Why should you un-manage your work? You should use this snap-in if you want to reduce work about work. Let machines manage issues, including creating and updating statuses, so developers can focus on work that matters. You’ll resonate with this, if you have ever:

- Delivered a hot-patch and realized you never had an issue to track 
- Or just felt that creating and managing issues is a distractio
If your team’s best practice is to link your GitHub activity to an existing issue-ID during branch creation, commits and PRs, then this snap-in will honor that and enable a GitHub driven issue state, without auto creating issues. [Here](https://devrev.ai/docs/integrations/github#github-events) are the different ways you can link your DevRev issue to GitHub branches, commits and PRs.


## How it works


## Features


**Automatic status updates**

You can associate GitHub commits, branches and pull requests with the DevRev issue they correspond to. Doing so allows you to see GitHub activity in the corresponding DevRev issue and to act on those events, allowing you to automate away your manual tasks. Mention DevRev issues in GitHub, and route the relevant GitHub events to this issue. They can be mentioned either as display IDs (ISS-34) or object IDs (issue:34), case insensitively. A DevRev issue can be mentioned in branch names, commit messages or PR titles.

**Autocreate issues from GitHub branch**

If you do not explicitly associate your DevRev issue to GitHub branches, commits or PRs, then we can autocreate your issues so you have an account of all your GitHub activity. This feature automatically creates an issue when a new branch is created, and tracks all associated commits and Pull Requests on this issue. The auto-created issues will move status based on Git activity, to in development based on branch and commit activity, and in review when PRs are created. When PRs are merged, the issue will be automatically closed, though this behavior is configurable.

**Autocreate issues from GitHub PRs**

You can choose to automatically create issues when a new PR is created, and it is not linked to an existing DevRev Issue. The behavior is similar to how issues are auto-created with new branches. The auto-created issues will move status based on Git activity, and events are posted on the DevRev issue timeline. It is recommended you enable either one of `Autocreate issue from GitHub branch` or `Autocreate issue from GitHub PR`, but not both.

Issues autocreated from GitHub branches or PRs are called autonomous issues, and have the tag `autonomous`.

**Attribute part to autonomous work**

Autonomous issues originating from GitHub will be attributed to a default part. You can configure the default part while setting up your snap-in. Every issue in DevRev must have a part attribution.

**Enrich autonomous work descriptions**

Enrich autonomous issues with information derived from GitHub PR events. The title and description of an autocreated issue is enriched with the PR data. When a new GitHub PR is opened or edited, then the related autonomous issue description is updated with the latest PR description. If the user has removed the auto generated text, then the automation will no longer update the description from PRs. Similarly, autonomous work titles are updated with the PR title, if the user hasn’t already updated it.

**Link autonomous work with related issue**

Create a related link between the work-items mentioned in the PR body and the autonomous issues tagged with the branch/PR. When a new GitHub PR is opened/edited, for all the autonomous tagged work items(by branch/PR), automatically mark the issues mentioned in the PR as related.

**Automatically close autonomous work**

Autonomous work gets closed when its related PR is merged. However, if there is no PR activity on this work, then the autonomous work is closed after configurable period.

**GitHub Commands**

Enable quick actions to close or attribute a PR to DevRev issue(s) with slash command.

- `/towards` - Use the `/towards` command in the PR description to associate the related GitHub activity to the issue(s). This will ensure that the PR and issue are linked such that related events are posted and issue status is driven by GitHub events.

- `/close {work-id}` - Use `/close ISS-3 ISS-4` in a PR body to automatically close a specific issue(s) when the PR is merged. You can also use `/close #work` to close all associated issues with a PR when that PR is merged without knowing the specific ids.

**Automatic PR tasks**

When a pull request is requested or reopened, a DevRev task is created for you. In order for this automation to be triggerred, you'll need to link your Pull Requests to DevRev issues. If your PR is removed, merged or closed, then the Task gets deleted. However, if you submit your PR review, then the task is closed.

**Automatic PR reminders**

When a pull request is inactive for more than a specified number of days, then this automation will post a message in all related DevRev issues. You'll need to link your GitHub Pull Request to DevRev issue to enable these reminders. There are several ways to link your GitHub Pull Requests to DevRev Issues. You can do so by mentioning the DevRev issue-id in Pull Requests title or body, or mention it in the branch name or commit message. Reminders are also posted for issues created autonomously.

You can choose to setup the inactive period in number of days through the max_inactive_days setting.
