# Support Alerts Process

## Purpose

To establish a structured alerting system for customer support signals that require visibility and potential action. These alerts are sent to a shared Slack channel monitored by the support manager and relevant stakeholders to proactively manage customer experience, identify at-risk tickets, and ensure timely engineering follow-up.

## Alerting Philosophy

Support alerts serve as an early warning system. They're not just notifications — they’re signals that something in the support environment requires attention, decision-making, or intervention. The goal is to:

- Maintain visibility into new and high-risk tickets.
- React quickly to customer dissatisfaction.
- Track the health and responsiveness of engineering escalations.
- Detect escalation signals in natural language.

All alerts are generated from systems like Zendesk, Salesforce, or other support tools, and are formatted and sent via Zapier to Slack.

---

## Alert Types & Descriptions

### 1. New Ticket Created

**Description**: Triggers when a new customer ticket is created.  

**Slack Message Includes**:
- Customer name or account
- Ticket subject or short summary
- Ticket priority (Critical, High, Normal, Low)
- Link to the ticket  

**Purpose**: Provides immediate awareness of new issues. Helps spot high-priority tickets early.

---

### 2. Negative CSAT Received

**Description**: Triggers when a customer submits a CSAT survey with a poor rating.  

**Slack Message Includes**:
- Rating (e.g. “Bad”)
- Customer’s comment (if available)
- Link to the ticket  

**Purpose**: Surfaces negative feedback for immediate follow-up or investigation. Enables fast recovery or escalation.

---

### 3. Escalation Language Detected

**Description**: Triggers when certain customer language is detected in ticket replies.  
**Trigger Phrases (examples)**:
- “I’m frustrated”
- “It’s still broken”
- “This is unacceptable”
- “We may churn”  

**Slack Message Includes**:
- Customer name
- The triggering sentence or phrase
- Link to the ticket  

**Purpose**: Flags emotionally charged or escalating customer sentiment. Gives support leaders a chance to step in before it spirals.

---

### 4. New Engineering Escalation

**Description**: Triggers when a support engineer marks a ticket as escalated to engineering (e.g., via a custom field or tag).  

**Slack Message Includes**:
- Customer name
- Escalation reason or ticket subject
- Assigned engineer or team (if known)
- Link to the Zendesk/JIRA ticket  

**Purpose**: Keeps leadership informed of handoffs to engineering. Ensures accountability and timely follow-up.

---

### 5. Engineering Escalation Aged 14+ Days

**Description**: Triggers when an open engineering escalation has been unresolved for over 14 days.  

**Slack Message Includes**:
- Customer name
- Date escalated
- Original support ticket link
- Engineering ticket link (if applicable)  

**Purpose**: Surfaces stale escalations that may be stuck. Enables nudging, re-prioritizing, or closing the loop with the customer.

---

## Implementation Notes

- Alerts are generated using a combination of triggers in Zendesk, Salesforce, or other ticketing systems.
- Zapier is used for formatting the message, enriching it with context, and posting it to Slack.
- Alerts should post to a dedicated `#support-alerts` or `#cs-ops-alerts` channel.
- It’s helpful to include emojis, flags, or tags (e.g., 🔴 `#critical`, 📣 `#csat`) to aid scanning.

## Maintenance & Iteration

- Alert triggers should be reviewed quarterly to ensure relevance.
- Consider adding suppression logic to avoid alert fatigue (e.g., suppress similar alerts from the same customer within a 2-hour window).
- New alert types can be added as the team’s needs evolve.

---

_This alerting system is intended to help teams stay agile, proactive, and aligned with customer signals — not reactive or buried in dashboards._
