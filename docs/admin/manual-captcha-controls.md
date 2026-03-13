# Manual CAPTCHA Controls

## Overview

In addition to the automatic rules that trigger CAPTCHA challenges, administrators can manually enable CAPTCHA for specific requests or endpoints through the Admin Panel. This is useful during active security incidents, for targeted testing, or to proactively protect a high-risk endpoint.

Manual overrides take precedence over the automatic rules - an endpoint with a manual CAPTCHA enabled will always show a challenge, regardless of traffic patterns.

## Before You Begin

- You need **Admin Panel access** with the `Security Editor` role or higher.
- Manual overrides persist until explicitly disabled. They do not expire automatically.
- Enabling CAPTCHA broadly (e.g. for all requests) will affect all users, including legitimate ones. Use targeted overrides where possible.

## Enabling CAPTCHA Manually

1. Log in to the Admin Panel.
2. Navigate to **Security → CAPTCHA Controls**.
3. Click **Add Override**.
4. Configure the override:

| Field | Description |
|---|---|
| Scope | Choose whether to apply to all requests, a specific endpoint, or a specific request type. |
| Reason | Optional but recommended for audit trail purposes. |
| Notify team | Optional - sends a notification to [PLACEHOLDER: configured alert channel]. |

5. Click **Enable**.

The override takes effect immediately.

> [PLACEHOLDER: Screenshot - "Add Override" dialog with Scope, Reason, and Notify fields]

## Disabling a Manual Override

1. Navigate to **Security → CAPTCHA Controls**.
2. Find the active override in the list.
3. Click **Disable** and confirm.

The override is removed immediately. Automatic rules continue to apply as normal.

> [PLACEHOLDER: Screenshot - CAPTCHA Controls list view showing active overrides with Disable button]

## Common Use Cases

### During an active attack
If automated rules are not catching a specific attack pattern, an admin can manually enable CAPTCHA for the targeted endpoint while the engineering team investigates a permanent fix.

### QA and integration testing
CAPTCHA can be enabled for a specific test environment endpoint to verify that your integration handles CAPTCHA challenges correctly.

> [PLACEHOLDER: Link to "Testing CAPTCHA Integration - Developer Guide"]

### Proactive protection before a high-traffic event
If a product launch or campaign is expected to attract unusual traffic, CAPTCHA can be pre-enabled on sensitive endpoints as a precaution, then disabled once traffic normalises.

## Audit Log

All manual CAPTCHA changes are recorded in the audit log.

1. Navigate to **Security → Audit Log**.
2. Filter by **Event Type → CAPTCHA Override**.

> [PLACEHOLDER: Screenshot - Audit log filtered to CAPTCHA override events]

## Related Resources
- [CAPTCHA Trigger Rules](../security/captcha-trigger-rules.md)
- [IP Blacklist Management](../security/ip-blacklist-management.md)
- [Rate Limiting Overview](rate-limiting-overview.md)
