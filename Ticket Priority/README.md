# Zendesk to Engineering Priority Alignment Process

![image](https://github.com/user-attachments/assets/b23987ca-a75b-44e1-b229-483991aa2d9b)


## Purpose

To establish a consistent process for aligning Zendesk ticket priorities with corresponding Engineering (JIRA) priorities, ensuring clarity and urgency alignment between Support and Engineering teams in a B2B SaaS environment.

## Priority Mapping Overview

Zendesk ticket priorities should mirror Engineering JIRA issue priorities. Support tickets may start with an AI-generated priority, but agents are responsible for adjusting it based on evolving context, customer sentiment, and impact.

### Priority Mapping

| Zendesk Priority | JIRA Priority | Description                                                                 |
|------------------|---------------|-----------------------------------------------------------------------------|
| Critical         | Critical      | Full service disruption, security threats, or severe performance degradation. |
| High             | High          | Major functionality impaired or degraded, but a workaround exists.         |
| Normal           | Medium        | Limited impact or inconvenience; workaround available.                     |
| Low              | Low           | Minor issue, cosmetic bug, or feature request.                             |

## Critical Priority Examples

- Complete product outage or customers unable to log in.
- Confirmed security vulnerability or data exposure.
- Product performance degraded to the point of timeouts or unusability.
- Multi-tenant issue affecting multiple accounts or users.
- Any issue that risks violating an SLA.

## High Priority Examples

- Key product functionality not working (e.g., alerts not firing, data not ingesting).
- Bugs affecting a single customer but blocking core workflows.
- Frequent timeouts or crashes with workarounds.
- Syncs/integrations breaking in production for high-value customers.

## Normal Priority Examples

- Usability bugs with known workarounds.
- Feature not behaving as expected but not blocking work.
- Performance issues in non-critical flows.
- Intermittent errors that self-resolve.

## Low Priority Examples

- Typos, UI misalignment, or minor visual inconsistencies.
- Requests for UI/UX improvements.
- Feedback about non-core product behavior.

## Process for Setting and Updating Priorities

1. **Initial Assignment**: Ticket is triaged by AI with a suggested priority.
2. **Agent Review**: Agent validates or adjusts priority based on:
   - Customer impact (who is affected and how severely)
   - Scope (is it isolated or affecting many customers?)
   - Urgency (does it impact SLAs, renewals, or production use?)
3. **Escalation Criteria**:
   - If a ticket is escalated to Engineering, the Zendesk priority must match the JIRA priority.
   - Priorities must be reevaluated during triage meetings or when new information is available.
4. **Cross-functional Communication**:
   - Any changes to priority after escalation must be communicated in the triage or handoff channels.

## Response and Fix SLO Targets

### Critical
- **Zendesk Initial Response**: within 1 hour  
- **Engineering Initial Response**: within 2 hours  
- **Fix Expectation**: Bug should interrupt the current sprint and be fixed immediately

### High
- **Zendesk Initial Response**: within 4 hours  
- **Engineering Initial Response**: within 1 business day  
- **Fix Expectation**: Bug should be fixed in the next sprint

### Normal
- **Zendesk Initial Response**: within 2 business days  
- **Engineering Initial Response**: within 2 business days  
- **Fix Expectation**: Place bug in backlog with correct priority for future planning

### Low
- **Zendesk Initial Response**: within 2 business days  
- **Engineering Initial Response**: within 2 business days  
- **Fix Expectation**: Place bug in backlog with correct priority for future planning

## Tips for Agents

- Always escalate with clear reproduction steps, logs, screenshots, and customer impact summary.
- Be proactive in downgrading/upgrading tickets based on live data.
- Align with the customer-facing language: avoid labeling something critical unless it truly is.

## Triage Review Meetings

- Held daily or regularly between Support and Engineering.
- Confirm next steps on escalated tickets.
- Reassess ticket priorities together.

---

_This document should be version-controlled and reviewed quarterly to ensure relevance with current team workflows and product realities._
