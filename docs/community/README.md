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
| Sponsors tiers | `.github/sponsors.yml` | Reference only. The live tiers live in the Sponsors dashboard. |
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

## GitHub Sponsors

Brazil is a supported region for GitHub Sponsors, so the account is eligible to receive payouts. Enrollment is a manual process with four steps:

| Step | Where | State |
|---|---|---|
| 1. Two-factor authentication | Account settings | Done |
| 2. Sponsors profile | https://github.com/sponsors/Axelthebat | Pending |
| 3. Tax information | Sponsors dashboard, via Stripe | Pending |
| 4. Bank information | Sponsors dashboard, via Stripe | Pending |

Until step 2 is finished, `https://github.com/sponsors/Axelthebat` redirects to the profile overview, and the API rejects tier creation with `Axelthebat does not have a GitHub Sponsors profile`.

### Step 2: profile fields

**Short description** (90 characters, limit 100):

> Security tooling, Linux and networking. Open-source security tools in Rust, Go and Python.

**Full description** (506 characters, limit 1000):

> I build open-source security tooling around Linux, networks and cloud infrastructure.
>
> The work is small, sharp tools that solve a concrete problem: auditing Kubernetes manifests against CIS benchmarks, checking Linux hardening baselines, observing network traffic with eBPF, and Terraform modules for reproducible cloud infrastructure.
>
> Everything I maintain is MIT licensed and built in the open. If one of these tools saves you an afternoon, sponsorship keeps the coffee flowing and the homelab humming.

Set the featured item to the profile repository, `Axelthebat/Axelthebat`, and publish the profile.

### Steps 3 and 4

Stripe collects the tax and bank details. The bank account country must match the country of residence, and the identity details are difficult to change after submission, so check them before confirming. If a personal bank account is not an option, a fiscal host such as the Open Source Collective can receive the funds and pay them out.

### Tiers

Create these from the Sponsors dashboard, or through the `createSponsorsTier` GraphQL mutation once the profile is public:

| Amount | Description |
|---|---|
| $5 per month | Covers a coffee for a late night debugging session. |
| $25 per month | Keeps the homelab running and the coffee stock full. |
| $100 per month | Funds a full weekend of building open-source security tooling. |

The dashboard is the source of truth once the tiers exist. `.github/sponsors.yml` keeps the original intent and can be deleted or left as a record.

### Sponsor button

Add `.github/FUNDING.yml` only after the profile is live, otherwise the Sponsor button leads to a page that does not exist:

```yaml
github: Axelthebat
```
