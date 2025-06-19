# Pending ticket workflow

This workflow helps make sure tickets in a `pending` state are moving forward by automatically following up with the customer. If there's no response after a few reminders, the system will close the ticket—but not before giving the agent a heads-up.

## Overview

| Time in Pending | Action               | Customer Message | Agent Notification |
|-----------------|----------------------|------------------|--------------------|
| 2 business days | First reminder        | ✅               | —                  |
| 5 business days | Final reminder + warning | ✅          | —                  |
| 7 business days | Auto-close            | ✅               | ✅ (Slack + internal note) |

---

## Automation: 2-day pending reminder

Sends a friendly nudge to the customer 2 business days after a ticket goes into `Pending`.

### Trigger conditions

All of the following must be true:

- `Ticket: Status` is `Pending`  
- `Ticket: Brand` is `Sentry`  
- `Ticket: Hours since pending (business)` is `16`  
- `Ticket: Tags` does **not** contain `missed_reminder`

### Actions

- Sends an email to the customer using the following template:
  
```text
Subject: Just checking in on your support request

Hey there {{ticket.requester.first_name}},

Hope you're doing great! Just a quick nudge about your ticket – we're really looking forward to hearing back from you.

Oh, and here's a quick recap of your request:

{{ticket.comments_formatted}}

Cheers,  
The {{YOUR COMPANY NAME}} Support Team
