---
layout: page
title: Privacy Policy
permalink: /privacy/
---

# Privacy Policy

Last updated: 2026-02-23

This privacy policy describes how **Totoro (OpenClaw) ad assistant** (“we”, “our”) handles information when operating automation workflows for Meta Ads (Facebook/Instagram) and related reporting.

## What we collect

Depending on the workflow you run, we may process:

- **Meta Ads identifiers** (e.g., ad account ID, campaign/adset/ad IDs, page ID)
- **Performance metrics** retrieved via the Meta Marketing API (e.g., spend, impressions, clicks, conversions, ROAS)
- **User-provided content** for ads (e.g., ad copy, headlines, creative assets you upload)
- **Operational logs and audit records** (e.g., timestamps of actions, approval decisions, tool outputs)

We do **not** intentionally collect payment card numbers. If you paste secrets (e.g., access tokens) into chat, treat that as sensitive and rotate them immediately.

## How we use information

We use the information only to:

- Create, modify, and monitor advertising entities in Meta Ads (typically **PAUSED by default**)
- Generate reports and recommendations
- Provide auditability (approval logs / receipts) for write operations
- Debug issues and improve reliability of the automation workflow

## Where data is stored

- Data may be stored on the operator’s machine in tenant-scoped files (for example, approval logs and run artifacts).
- We do not sell or rent your information.

## Sharing

We share information only as needed to run the workflows:

- With **Meta Platforms, Inc.** via the Meta Marketing API when you request actions or reports.

## Data retention

Operational artifacts and logs are retained for as long as needed for auditability and troubleshooting, and may be deleted by the operator.

## Security

We use a tenant-scoped sandbox design to limit file access. Write operations are approval-gated where configured.

## Your choices

You can request deletion of locally stored artifacts/logs by the operator.

## Contact

For questions about this policy, contact: **degmail (per operator request)**
