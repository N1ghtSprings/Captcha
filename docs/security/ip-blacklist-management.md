# IP Blacklist Management

## Overview

The IP blacklist is a list of IP addresses that are blocked from interacting normally with the service. Any request from a blacklisted IP immediately triggers a CAPTCHA challenge, regardless of request volume or behavior.

This article explains how to view, add to, and remove entries from the blacklist using the Admin Panel.

## Before You Begin

- You need **Admin Panel access** with at minimum the `Security Viewer` role to view the blacklist, and `Security Editor` to make changes.
- Changes to the blacklist take effect **immediately** -  there is no staging or review step.
- Removing an IP from the blacklist lifts the CAPTCHA trigger for that IP right away.

> [PLACEHOLDER: Link to "Admin Panel -  Roles and Permissions"]

## Viewing the Blacklist

1. Log in to the Admin Panel.
2. Navigate to **Security →  IP Blacklist**.
3. The list displays all currently blacklisted IPs, the date they were added, the reason (if recorded), and the admin who added them.

> [PLACEHOLDER: Screenshot -  IP Blacklist list view with columns: IP Address, Date Added, Reason, Added By]

You can search by IP address using the search bar at the top of the list.

## Adding an IP to the Blacklist

1. In the IP Blacklist view, click **Add IP**.
2. Enter the IP address or CIDR range (e.g. `192.168.1.1` or `192.168.1.0/24`).
3. Enter a reason -  this is optional but strongly recommended for audit purposes.
4. Click **Confirm**.

The IP is added immediately. Any in-flight requests from that IP are not affected - the rule applies to subsequent requests only.

> [PLACEHOLDER: Screenshot -  "Add IP" dialog with fields: IP Address, Reason, Confirm button]

!!! note
    You can blacklist an entire subnet by entering a CIDR range. Use this carefully -  a broad range may affect legitimate users on the same network.

## Removing an IP from the Blacklist

1. In the IP Blacklist view, find the IP address using the search bar.
2. Click the **Remove** button next to the entry.
3. Confirm the removal in the dialog.

The IP is removed immediately and will no longer trigger a CAPTCHA based on the blacklist rule. Other rules (such as request volume) may still apply.

> [PLACEHOLDER: Screenshot -  Removal confirmation dialog]

## Bulk Operations

> [PLACEHOLDER: Documentation of the process if supported]

## Audit Log

All changes to the blacklist are recorded in the audit log. To view:

1. Navigate to **Security →  Audit Log**.
2. Filter by **Event Type →  Blacklist Change**.

> [PLACEHOLDER: Screenshot -  Audit log filtered to blacklist events]

## Frequently Asked Questions

**What happens to a user who is already mid-session when their IP is blacklisted?**  
> [PLACEHOLDER]

**Can I temporarily blacklist an IP and have it auto-expire?**  
> [PLACEHOLDER]

**Does the blacklist apply to all endpoints or can it be scoped?**  
> [PLACEHOLDER]

## Related Resources
- [Bot Protection Overview](bot-protection-overview.md)
- [CAPTCHA Trigger Rules](captcha-trigger-rules.md)
- [Manual CAPTCHA Controls](../admin/manual-captcha-controls.md)
- [Rate Limiting Overview](../admin/rate-limiting-overview.md)
