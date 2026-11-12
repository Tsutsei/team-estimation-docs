---
layout: page
title: Security policy
permalink: /security/
---

_Last updated: 11 November 2026_

This policy applies to the Atlassian Marketplace app **Team Estimation – Sizing Board & Planning Poker for Jira** (the "App"), provided by **Tsutsei Software**, a brand of the sole trader identified on the [Legal information](https://tsutsei-software.com/legal.html) page ("we").

## Reporting a vulnerability
Send security issues to **[security@tsutsei-support.atlassian.net](mailto:security@tsutsei-support.atlassian.net)**. Every message creates a tracked request in our support system. Please include the app, your site URL, steps to reproduce and the impact you expect. Do not include passwords, API tokens or customer data.

We confirm receipt within 2 business days, keep you informed about the fix and credit you in the release notes if you wish. Please give us reasonable time to release a fix before disclosing the issue publicly.

## Architecture
- The App runs entirely on **Atlassian Forge** ("Runs on Atlassian"): Forge functions, Forge SQL, Forge Realtime and Custom UI served by Atlassian. No Forge Remote, no egress to external servers, no vendor-side servers or copies of customer data.
- The App stores **ids only**: for each estimation session the ids of its work items, the lanes and votes, and the account ids of participants, in each customer's Forge SQL database, encrypted at rest and in transit by Atlassian. It stores no summaries, descriptions or other content of work items and no names or e-mail addresses.
- Work items are read and written in the user's browser with the signed-in user's permissions, so everyone sees only the work items Jira shows them, and estimates are saved only where the saving user may edit. The backend never receives the content of work items.
- The App requests only the scopes its features need and never asks for passwords or API tokens.
- The App does not use AI or machine-learning models, and no customer data is processed by such models.

## Secure development
- Votes are hidden on the server: until a moderator reveals a card, a participant receives only their own vote and the list of people who have voted. Only moderators (the creator, co-moderators and Jira administrators) can reveal, close, delete or save.
- Requests from the browser are validated (ids, lanes of the session, value formats, limits); all SQL uses bound parameters; all text is added to the page as text, never as HTML; copied result tables are guarded against spreadsheet formula injection.
- Logs contain error messages only, never work item content or votes. Access to logs is limited to the developer (Forge developer console).
- Every change passes automated unit and end-to-end tests (including permission checks) before it is deployed to production.
- Dependencies are checked with `npm audit` before every release; known vulnerabilities are fixed before deploying.

## Access control
- Source code is in private GitHub repositories; GitHub and Atlassian accounts are protected with two-factor authentication.
- The developer workstation uses full-disk encryption, automatic operating system and security updates, a firewall and malware protection. Unsupported operating system versions are not used.
- Access to source code, the Forge developer console, the Marketplace partner account and the support site is reviewed every quarter.

## Fixing vulnerabilities
Vulnerabilities are scored with CVSS and fixed within the deadlines of the Atlassian Marketplace security bug fix policy:

| Severity | CVSS | Fix released within |
|---|---|---|
| Critical | 9.0 – 10.0 | 10 days |
| High | 7.0 – 8.9 | 4 weeks |
| Medium | 4.0 – 6.9 | 12 weeks |
| Low | 0.1 – 3.9 | 25 weeks |

Forge deployments reach all installations within minutes, so customers do not need to update the App.

## Security incidents
If a security incident may affect customer data, we report it to Atlassian within 24 hours and notify the admins of affected sites within 72 hours where possible. As a data processor under the GDPR, we inform controllers without undue delay. See also the [privacy policy]({{ '/privacy/' | relative_url }}) and the [Data Processing Addendum]({{ '/dpa/' | relative_url }}).
