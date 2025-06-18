## 🚦 Automated Zendesk Ticket Triage Workflow (via Zapier, OpenAI, Slack)

### **Overview**
When a new ticket is created in Zendesk, this workflow:
1. Analyzes the ticket with OpenAI to:
   - Set ticket priority
   - Detect if it’s a critical/system-down issue
   - Generate a customer issue summary
2. Updates the ticket in Zendesk with these details
3. Notifies your team in Slack

---

### **Workflow Steps**

#### 1. **Trigger: New Zendesk Ticket**
- **Zapier Trigger:** “New Ticket in Zendesk”
- **Action:** Fires whenever a new ticket is created.

#### 2. **Action: Analyze Ticket with OpenAI**
- **Zapier Action:** “Send Prompt to OpenAI (GPT-4)”
- **Prompts:**
  - **Priority Prompt:**  
    _“Given the following Zendesk ticket, assign a priority (Low, Medium, High, Urgent): [Ticket Subject + Description]”_
  - **Criticality Prompt:**  
    _“Is this ticket describing a critical issue (e.g., system down, outage, security incident)? Answer Yes or No and explain.”_
  - **Summary Prompt:**  
    _“Summarize the customer’s issue in 1-2 sentences: [Ticket Subject + Description]”_

- **Zapier Tip:** You can use multiple “OpenAI” actions for each prompt, or combine them into one prompt and parse the response.

#### 3. **Action: Update Zendesk Ticket**
- **Zapier Action:** “Update Ticket in Zendesk”
- **Fields to Update:**
  - **Priority:** Set from OpenAI response
  - **Custom Field (Critical):** Set Yes/No from OpenAI response
  - **Internal Note or Custom Field (Summary):** Add OpenAI-generated summary

#### 4. **Action: Send Slack Notification**
- **Zapier Action:** “Send Channel Message in Slack”
- **Message Template:**
  ```
  :ticket: *New Zendesk Ticket*  
  *Subject:* [Ticket Subject]  
  *Priority:* [OpenAI Priority]  
  *Critical:* [OpenAI Criticality]  
  *Summary:* [OpenAI Summary]  
  *Link:* [Zendesk Ticket URL]
  ```

---

### **Example Zapier Setup**

1. **Trigger:** Zendesk → New Ticket
2. **Action:** OpenAI → Prompt for Priority
3. **Action:** OpenAI → Prompt for Criticality
4. **Action:** OpenAI → Prompt for Summary
5. **Action:** Zendesk → Update Ticket (priority, critical, summary)
6. **Action:** Slack → Send Channel Message

---

### **Tips**
- You can combine OpenAI prompts for efficiency, but parsing the response may require a Formatter step in Zapier.
- Make sure your Zendesk fields (priority, custom fields) are mapped correctly.
- Test with sample tickets to fine-tune your prompts for best results.

---

**This workflow ensures every new ticket is triaged quickly, critical issues are flagged, and your team is notified in real time.**
