# Gitcord

[![Discord.js](https://img.shields.io/badge/Discord.js-14.x-5865F2?style=flat-square&logo=discord&logoColor=white)](https://discord.js.org)
[![GitHub API](https://img.shields.io/badge/GitHub_API-Powered-181717?style=flat-square&logo=github&logoColor=white)](https://docs.github.com/en/rest)
[![Firebase](https://img.shields.io/badge/Firebase-Secured-FFCA28?style=flat-square&logo=firebase&logoColor=black)](https://firebase.google.com)
[![Redis](https://img.shields.io/badge/Redis-Cached-DC382D?style=flat-square&logo=redis&logoColor=white)](https://redis.io)
[![AES-256](https://img.shields.io/badge/Encryption-AES--256-00897B?style=flat-square&logo=letsencrypt&logoColor=white)](https://en.wikipedia.org/wiki/Advanced_Encryption_Standard)
[![OAuth 2.0](https://img.shields.io/badge/Auth-OAuth_2.0-4285F4?style=flat-square&logo=oauth&logoColor=white)](https://oauth.net/2/)
[![Node.js](https://img.shields.io/badge/Node.js-18%2B-339933?style=flat-square&logo=nodedotjs&logoColor=white)](https://nodejs.org)
[![JavaScript](https://img.shields.io/badge/JavaScript-ES2022-F7DF1E?style=flat-square&logo=javascript&logoColor=black)](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
[![Platform](https://img.shields.io/badge/Platform-Discord-5865F2?style=flat-square&logo=discord&logoColor=white)](https://discord.com)
[![Status](https://img.shields.io/badge/Status-Live-brightgreen?style=flat-square)](https://discord.com)

> **GitHub management for Discord.** 37 slash commands. Zero context-switching.

Gitcord bridges your entire GitHub workflow into Discord — create repos, review PRs, manage issues, and ship releases without ever leaving your server. Every command responds with rich, paginated Discord V2 Component UI, encrypted credential handling, and real-time data pulled directly from GitHub.

---

## Experience

```
╔══════════════════════════════════════════════════════════════════════════╗
║  Discord  ·  #dev-team                                          ⊟  ⊡  ✕ ║
╠══════════════════════════════════════════════════════════════════════════╣
║                                                                          ║
║  ┌──────────────────────────────────────────────────────────────────┐   ║
║  │  ◈  Gitcord                                          [Live]  ●   │   ║
║  ├──────────────────────────────────────────────────────────────────┤   ║
║  │                                                                  │   ║
║  │   > /repo create  ░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░   │   ║
║  │                                                                  │   ║
║  │   ╭─────────────────────────────────────────────────────────╮   │   ║
║  │   │  ✓  Repository Created                                  │   │   ║
║  │   │  ─────────────────────────────────────────────────────  │   │   ║
║  │   │   Name        ·  my-awesome-project                     │   │   ║
║  │   │   Visibility  ·  Private                                │   │   ║
║  │   │   URL         ·  github.com/you/my-awesome-project      │   │   ║
║  │   │   Created     ·  just now                               │   │   ║
║  │   ╰─────────────────────────────────────────────────────────╯   │   ║
║  │                                                                  │   ║
║  │   > /pr create  ░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░   │   ║
║  │                                                                  │   ║
║  │   ╭─────────────────────────────────────────────────────────╮   │   ║
║  │   │  ⇄  Pull Request Opened                    #42  · Open  │   │   ║
║  │   │  ─────────────────────────────────────────────────────  │   │   ║
║  │   │   Title    ·  feat: add authentication module           │   │   ║
║  │   │   Base     ·  main  ←  feature/auth                     │   │   ║
║  │   │   Checks   ·  ● ● ●  3 passing                          │   │   ║
║  │   │  ┌──────────────────┐  ┌──────────────────┐             │   │   ║
║  │   │  │   Merge PR       │  │   View on GitHub │             │   │   ║
║  │   │  └──────────────────┘  └──────────────────┘             │   │   ║
║  │   ╰─────────────────────────────────────────────────────────╯   │   ║
║  │                                                                  │   ║
║  │   > /issue list  ░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░   │   ║
║  │                                                                  │   ║
║  │   ╭─────────────────────────────────────────────────────────╮   │   ║
║  │   │  ◎  Open Issues  ·  my-awesome-project       Page 1/3   │   │   ║
║  │   │  ─────────────────────────────────────────────────────  │   │   ║
║  │   │   #12  ·  Bug: login redirect fails on mobile           │   │   ║
║  │   │   #11  ·  Feature: dark mode support                    │   │   ║
║  │   │   #10  ·  Chore: update dependencies                    │   │   ║
║  │   │   #9   ·  Bug: rate limit not respected                 │   │   ║
║  │   │   #8   ·  Feature: export to CSV                        │   │   ║
║  │   │  ┌────────────┐  ┌────────────┐  ┌──────────────────┐  │   │   ║
║  │   │  │  ◀  Prev   │  │   Next  ▶  │  │   Create Issue   │  │   │   ║
║  │   │  └────────────┘  └────────────┘  └──────────────────┘  │   │   ║
║  │   ╰─────────────────────────────────────────────────────────╯   │   ║
║  │                                                                  │   ║
║  └──────────────────────────────────────────────────────────────┘   ║
║                                                                          ║
║   ┌──────────────────────────────────────────────────────────────┐      ║
║   │  Message #dev-team                                           │      ║
║   └──────────────────────────────────────────────────────────────┘      ║
╚══════════════════════════════════════════════════════════════════════════╝
```

---

## Commands

Gitcord ships **37 slash commands** across 9 categories. All commands require a linked GitHub account. Use `/auth link` once to connect — every command after that just works.

---

### Repositories

#### `/repo create`
Create a brand-new GitHub repository directly from Discord. Specify the repository name, set it as public or private, add an optional description, and choose whether to initialize it with a README. Gitcord returns a confirmation card with the full repository URL, visibility status, default branch, and a direct link to open it on GitHub.

#### `/repo list`
Fetch a paginated list of all repositories owned by your linked GitHub account. Results are displayed in a compact, scrollable Component V2 embed with repository names, visibility badges (public/private), star counts, primary language, and the date last pushed. Navigate forward and backward through pages using the built-in buttons.

#### `/repo info`
Pull a detailed snapshot of any repository — yours or anyone else's public repo. Displays the full description, topics, license, open issue count, fork count, star count, watcher count, default branch, repository size, and the most recent push timestamp. Also shows whether the repo has a wiki, discussions, or GitHub Pages enabled.

#### `/repo delete`
Permanently delete a repository from your GitHub account. Gitcord shows a confirmation prompt with the repository name before executing — you must confirm before deletion proceeds. Returns a success message with the deleted repository's name once complete.

#### `/repo fork`
Fork any public GitHub repository into your account. Provide the owner and repository name, and Gitcord will create the fork, then respond with your new fork's URL, the upstream (original) repository it was forked from, and the default branch.

#### `/repo visibility`
Toggle a repository between public and private without visiting GitHub. Specify the repository name and the desired visibility. Gitcord updates the setting and confirms the change with the new visibility state and a link to the repository.

#### `/repo rename`
Rename an existing repository in your account. Provide the current repository name and the new name. Gitcord applies the rename and returns the updated repository URL, noting that existing clones pointing to the old URL will automatically redirect.

#### `/repo topics`
View or update the topic tags attached to a repository. When viewing, returns all current topics as a list. When setting, replaces the topic list with the ones you provide (comma-separated). Topics improve discoverability on GitHub and Gitcord displays them as styled tags in the response.

---

### Pull Requests

#### `/pr create`
Open a new pull request on any repository you have write access to. Specify the repository, a title, the head branch (the branch with your changes), and the base branch (where you want to merge). Optionally add a body/description. Gitcord returns the PR number, URL, assigned reviewers if any, and the CI status checks if they are already running.

#### `/pr list`
List all open pull requests on a repository in a paginated embed. Each entry shows the PR number, title, author, the head and base branches, how many commits it contains, whether it has any review requests, and when it was last updated. Navigate pages with arrow buttons.

#### `/pr view`
View the full details of a specific pull request by number. Returns the PR title, description/body, author, labels, assignees, reviewers and their review statuses (approved / changes requested / pending), number of changed files, additions and deletions, and the current merge status. Also shows any failing CI checks.

#### `/pr merge`
Merge an open pull request directly from Discord. Choose the merge strategy — merge commit, squash, or rebase. Gitcord confirms the merge and returns the resulting commit SHA, the branch that was merged, and whether the head branch was automatically deleted after merging.

#### `/pr close`
Close an open pull request without merging it. Gitcord marks the PR as closed and confirms with the PR number, title, and the reason field if one was provided. The PR remains in GitHub's history and can be re-opened at any time.

#### `/pr review`
Submit a review on an open pull request. Choose between Approve, Request Changes, or Comment. Add an optional review body to explain your feedback. Gitcord submits the review under your GitHub account and returns a confirmation with your review type and the PR it was submitted against.

---

### Issues

#### `/issue create`
Open a new issue on any repository you have access to. Provide a title, an optional body with full markdown support, labels to apply, and assignees from the repository's contributor list. Gitcord creates the issue and returns the issue number, URL, and a summary of applied labels and assignees.

#### `/issue list`
List open issues on a repository in a paginated embed. Each entry displays the issue number, title, author, label tags, assignee, comment count, and how long ago it was opened or updated. Supports filtering by label — pass a label name to narrow results to a specific category.

#### `/issue view`
View the complete details of a specific issue by number. Returns the full title, body (markdown rendered as plain text), author, all applied labels with their colors, assignees, milestone if set, comment count, and the current open/closed state with timestamps.

#### `/issue close`
Close an open issue by number. Gitcord marks the issue as closed on GitHub and returns confirmation with the issue title, number, and the closing timestamp. Optionally provide a comment that will be posted before the issue is closed, explaining why it was resolved.

#### `/issue assign`
Assign one or more collaborators to an open issue. Provide the issue number and the GitHub usernames to assign. Gitcord updates the assignees list and confirms with the full list of users now assigned to the issue. Can also be used to clear all assignees by passing an empty value.

---

### Releases

#### `/release create`
Create a new release on a repository. Provide a tag name (e.g., `v1.2.0`), a release title, and optional release notes written in markdown. Choose whether to mark it as a prerelease or as the latest release. Gitcord publishes the release and returns the release URL, tag, title, and whether it is flagged as a prerelease.

#### `/release list`
List all published releases for a repository in a paginated embed. Each entry shows the release tag, title, whether it is marked as the latest or a prerelease, the number of assets attached, the total download count across all assets, and the publication date.

#### `/release view`
View the full details of a specific release by tag name. Returns the release title, markdown-formatted release notes (as plain text), the list of attached binary assets with individual download counts, the release author, and publication timestamp. Also shows the source code archive links (.zip and .tar.gz).

#### `/release delete`
Delete a published release by tag name. Gitcord shows a confirmation prompt before deleting. Deleting a release does not delete the underlying git tag — only the release notes and assets are removed from GitHub Releases. Returns confirmation with the tag name that was affected.

---

### Gists

#### `/gist create`
Create a new GitHub Gist from Discord. Provide a filename with its extension, the file content, an optional description, and choose whether the gist should be public or secret. Gitcord creates the gist and returns the gist URL, the unique gist ID, and a direct link to the raw file content.

#### `/gist list`
List all gists owned by your linked GitHub account. Each entry shows the gist description or filename, whether it is public or secret, the number of files it contains, the number of forks and stars, and when it was last updated. Navigable across pages with forward and back buttons.

#### `/gist view`
View the full content of any gist by its ID. Returns the gist description, a list of all files it contains, and the full raw content of each file rendered inside a code block. Also shows the number of comments, forks, and the original creation date.

#### `/gist delete`
Delete a gist from your account by its ID. Gitcord confirms the deletion and returns the gist ID and description that was removed. This action is permanent — deleted gists cannot be recovered.

---

### Search

#### `/search repos`
Search GitHub's entire public repository index using a keyword query. Results include repository name, owner, description, primary language, star count, fork count, and last updated date — sorted by relevance or stars. Returns paginated results you can browse without leaving Discord.

#### `/search code`
Search for code across all of GitHub using a keyword or pattern. Optionally scope the search to a specific language, repository, or organization. Each result shows the matching file path, the repository it belongs to, and the matched line(s) of code with context. Ideal for finding usage examples, API references, or specific function names across the open-source ecosystem.

#### `/search users`
Search GitHub for user accounts and organization profiles by username or display name. Each result shows the GitHub username, display name, public repository count, follower count, and a link to their profile page. Useful for finding collaborators or verifying GitHub handles.

#### `/file view`
Fetch and display the raw contents of any file in any public GitHub repository. Provide the owner, repository name, file path, and optionally a branch or commit SHA. Gitcord renders the file content in a code block with the correct language detected from the file extension. Supports files up to the Discord embed size limit.

---

### Profile

#### `/profile`
Display a rich summary of your linked GitHub profile. Shows your display name, username, bio, location, company, website, public repository count, total stars received across all repos, follower and following counts, total public gist count, account creation date, and whether you have GitHub Pro or GitHub Sponsors active on your account.

#### `/auth link`
Begin the process of linking your GitHub account to Gitcord. Sends you a secure, time-limited authentication link via Discord DM. Opening the link takes you through a standard GitHub OAuth authorization screen where you grant Gitcord the permissions it needs. Once authorized, your credentials are encrypted and stored — you will not need to re-authenticate unless you explicitly unlink.

#### `/auth unlink`
Remove the connection between your Discord account and your GitHub account. Gitcord deletes all stored credentials associated with your Discord user ID. After unlinking, GitHub commands will no longer work until you run `/auth link` again.

---

### Notifications

#### `/notify subscribe`
Subscribe your current Discord channel to receive event notifications from a specific GitHub repository. Choose which event types to receive — push events, pull request activity, issue activity, release publications, or all of the above. Once subscribed, Gitcord will post a formatted notification card in the channel whenever a matching event fires on that repository.

#### `/notify unsubscribe`
Remove an active notification subscription. Specify the repository you want to stop receiving notifications from. Gitcord removes the subscription and confirms the repository name and channel the subscription was removed from. After unsubscribing, no further event notifications will be delivered to that channel for that repository.

---

### Utility

#### `/help`
Display the full Gitcord command list organized by category. Each entry shows the command name and a one-line description of what it does. Also shows your current GitHub account link status — whether you have a GitHub account connected or not. If you are not yet linked, the help response includes a prompt to run `/auth link` to get started.

---

## Security

Gitcord stores credentials using AES-256 encryption. Your GitHub token is never exposed in bot responses, logs, or Discord messages. Each user's credentials are isolated — no one else can access or use your linked account. You can revoke access at any time from within Discord using `/auth unlink`, or directly from your GitHub account's authorized OAuth applications page.

---

## License

Private project — all rights reserved. © 2025 JLAJ.
