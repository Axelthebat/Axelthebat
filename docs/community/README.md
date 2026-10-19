# Community setup

The repository files under `.github/` are the durable part of the community setup and are versioned with the code. Three steps live in the GitHub interface and are not stored in the repository. This file records what is done and what is left.

## Already applied

| Item | Where | State |
|---|---|---|
| Discussions enabled | Repository > Settings > Features | Enabled, six categories created |
| Category forms | `.github/DISCUSSION_TEMPLATE/` | Five forms, one per category (polls have no form support) |
| Issue templates | `.github/ISSUE_TEMPLATE/` | Bug report, feature request, and a chooser that routes questions to Discussions |
| Security policy | `SECURITY.md` | Private reporting via GitHub advisories |
| Code of Conduct | `CODE_OF_CONDUCT.md` | Contributor Covenant 2.1 |
| Contributing guide | `CONTRIBUTING.md` | Conventions, commit format, and where each kind of post belongs |
| License | `LICENSE` | MIT |
| Welcome discussion | [Discussion #1](https://github.com/Axelthebat/Axelthebat/discussions/1) | Created in Announcements |
| Sponsors tiers | `.github/sponsors.yml` | Requires the Sponsors profile to be activated in settings |
| Private vulnerability reporting | Repository > Settings > Security | Enabled |

## Manual steps remaining

### 1. Set the "Start a new discussion" template

Repository > Settings > Features > **Set up discussions** > edit the "Start a new discussion" field > paste the contents of [`WELCOME_TEMPLATE.md`](WELCOME_TEMPLATE.md) > **Start discussion**.

The template is stored by GitHub in repository settings, not in a file. The source is kept here so it can be regenerated or adjusted.

### 2. Pin the welcome discussion

Open [Discussion #1](https://github.com/Axelthebat/Axelthebat/discussions/1) > **Pin discussion**. GitHub exposes no API for this, so it has to be done in the interface.

### 3. Remove the emoji from the category names

Discussions > click the pencil next to a category > clear the emoji field > save.

The categories are created by GitHub with these default emoji:

| Category | Default emoji |
|---|---|
| Announcements | `:mega:` |
| General | `:speech_balloon:` |
| Ideas | `:bulb:` |
| Polls | `:ballot_box:` |
| Q&A | `:pray:` |
| Show and tell | `:raised_hands:` |

## Verifying

After the manual steps, `POST /repos/Axelthebat/Axelthebat/discussions` with a `category_id` returns a rendered form instead of a plain text box, which confirms the category forms were picked up.
