# Goal: Use Gmail mcp server to get a summary for my emails with Notion project integration

Please read my important unread emails from the last 7 days only. Use the Gmail MCP server efficiently by:

1. **Primary search:** `is:unread is:important after:[7_days_ago_date]`
2. **Account alerts:** `is:unread is:important (alert OR warning OR suspend OR balance OR "action needed")`
3. **Property specific:** `is:unread is:important (Ambria OR Amanda OR Yaprak OR Golden Meadows)`
4. **Business critical:** `is:unread is:important (meeting OR invite OR invoice OR payment OR urgent OR ASAP)`
5. **ONLY if no important results:** `is:unread after:[7_days_ago_date]` (fallback to all unread)
6. Limit initial results to 15 emails max (focus on quality over quantity)

## Notion Project Context Integration

For each email category, after reading email content:

1. **Search Notion projects database** for related projects using keywords from:
   - Sender company names (Vita, MYHC, Seamless Care, Bell, Westmount)
   - Project names (RHPA Training, LM365 Integration, Account Transfer)
   - Technical terms (API, integration, training, fiber, portal)
   - Client/stakeholder names

2. **Retrieve project pages** for matches and include:
   - Project status (Active/Planning/Completed/On Hold)
   - Key stakeholders and contacts
   - Current phase/milestone
   - Budget/timeline information
   - Recent updates or blockers

3. **Cross-reference email actions** with project status:
   - Link email requests to existing project tasks
   - Identify new project opportunities
   - Flag potential project updates needed
   - Note timeline impacts or scope changes

## Project Discovery Workflow

### Step 1: Extract Project Keywords
From each email, identify:
- Company/organization names
- Project codenames or references
- Technical terms (API, integration, training)
- Timeline references and deadlines
- Budget/cost mentions
- Stakeholder names and roles

### Step 2: Search Notion Database
Use Notion MCP to search for projects containing:
- Exact company matches
- Similar project themes
- Related stakeholders
- Technology stack overlap
- Timeline intersections

### Step 3: Project Context Summary
For each email with project matches:
- Current project health (on track/at risk/blocked)
- Recent activity or updates needed
- Stakeholder alignment status
- Next milestone dates
- Budget status

6. **Prioritize reading full content** for emails that are:
   - **Property management related** (Ambria, Amanda, tenants)
   - **Financial/payment related** (invoices, payments, account alerts)
   - **Meeting invitations or scheduling**
   - **Auto-replies that provide useful info** (timelines, contact details)
   - **Security/account alerts** (low balance, service disruptions)
   - **Action items requiring immediate response**

7. **Skip full content reading** for:
   - Marketing/promotional emails (unless from known business contacts)
   - Auto-replies that are just "message received" confirmations
   - Newsletter/educational content (Skool, Ndax, Trello, etc.)
   - Social media notifications and community updates
   - Old emails (>30 days) unless specifically urgent
   - Any email not marked as "important" by Gmail's algorithm

For each email category, provide:
- Email ID (for follow-up actions)
- Thread ID (for conversation tracking)
- Subject line
- Sender name and email
- Date received
- **Detailed summary with specific bullet points** including:
  - Main topic/issue discussed
  - Specific details, numbers, dates, names mentioned
  - Recommendations or solutions provided
  - Attachments or resources referenced
  - Timeline or next steps indicated
  - Key stakeholders or contacts involved
- Required action
- Suggested response (if needed)

Format the output as:

## 📧 Last 7 Days Email Summary & Actions

### Email Categories & Status
When categorizing emails, include status indicators:
- 🏠 **Property Management** (Ambria, tenants, contractors)
- 💰 **Financial** (invoices, payments, bank alerts)
- 📅 **Meetings** (invitations, scheduling, calendar)
- ⚠️ **Urgent Alerts** (service disruptions, security)
- 🔔 **Action Required** (responses needed)
- 📧 **Auto-Replies** (useful vs. acknowledgment only)
- 🏷️ **Promotional** (low priority marketing)

### Category Name (e.g., 💰 Financial, 📅 Meetings, 🔔 Urgent)

**[Email Number]. [Subject]**
- **ID:** [messageId] | **Thread:** [threadId]
- **From:** [Name] ([email])
- **Date:** [Date]
- **Related Project:** [Notion page title/link if found] | **Status:** [Current status from Notion]
- **Summary:** [1-sentence overview], then detailed bullet points:
  - • [Key point 1: main issue/topic]
  - • [Key point 2: specific details/numbers/dates]
  - • [Key point 3: recommendations/suggestions provided]
  - • [Key point 4: attachments/resources mentioned]
  - • [Key point 5: next steps/timeline indicated]
- **Project Impact:** [How this email affects project timeline/scope/budget]
- **Action Required:** [Specific action needed]
- **Project Action:** [Update needed in Notion project page]
- **Recommended Reply:** [Suggested response or "None needed"]

End with:
### 🎯 Priority Actions (Project-Aware)

[For each action, include project context]

1. **[Action] - Project: [Notion Page Name]**
   - Current Status: [status]
   - Impact: [how this action affects project]
   - Timeline: [project milestone this relates to]

### 📊 Project Dashboard Updates Needed
- **[Project Name]:** Update status to reflect [email content]
- **[Project Name]:** Add new stakeholder [person] from email
- **[Project Name]:** Timeline adjustment needed based on [email info]
- **[Project Name]:** Budget/scope change required

### 📌 Quick Actions Available
- **Mark as read:** "Mark emails #[number]. [subject] - [ID] as read"
- **Send draft:** "Send the draft for [subject] to [recipient]"
- **Create email:** "Create draft reply to [subject] saying [message]"
- **Archive emails:** "Archive emails #[number]. [subject] - [ID]"
- **Label emails:** "Label emails #[number]. [subject] - [ID] with [label_name]"
- **Check for new emails:** "Check for new important unread emails"

Examples:
- "Mark emails #1. Your Interactive Brokers Account - 19711001dc08d666, #4. RHPA Training - 1970d2473ae98f6c as read"
- "Archive emails #5. Your Home Investment - 1970d2c2fb976be4, #2. Invoices due - 196edad436c34c1b"
- "Label emails #1. Interactive Brokers - 19711001dc08d666 with Finance"

## Email Signature Integration

When creating ANY emails (drafts, replies, or direct sends), ALWAYS include the professional signature:

### Required Signature Format:
- **MIME Type:** `text/html` (required for image display)
- **Include both `body` and `htmlBody` parameters**
- **Signature HTML:** 
```html
<img src="https://drive.google.com/uc?export=view&id=1vfZgFtTwLvi3vII2k3CUZJIhrTmGl9pr" alt="Ahmed Younis - Merakey" style="width: 240px; height: auto; display: block;">
```

### Email Format Requirements:
```javascript
mimeType: "text/html"
body: "[Plain text version of email content]"
htmlBody: "[HTML version with proper HTML formatting and signature at end]"
```

### HTML Formatting Rules:
- **Use `<strong>` tags instead of `**` for bold text**
- **Use `<br>` tags instead of `\n` for line breaks**
- **Use proper HTML structure in `htmlBody`**
- **Never mix markdown syntax with HTML format**

### Example Implementation:
```
body: "Hi [Name],\n\nMeeting Details:\n- Date: Tuesday\n- Time: 1:00 PM\n\nBest,\nAhmed"

htmlBody: "Hi [Name],<br><br><strong>Meeting Details:</strong><br>- <strong>Date:</strong> Tuesday<br>- <strong>Time:</strong> 1:00 PM<br><br>Best,<br>Ahmed<br><br><img src='https://drive.google.com/uc?export=view&id=1vfZgFtTwLvi3vII2k3CUZJIhrTmGl9pr' alt='Ahmed Younis - Merakey' style='width: 240px; height: auto; display: block;'>"
```

**CRITICAL:** 
- Never send emails without the signature
- Always use HTML format for professional emails
- Use proper HTML tags (not markdown) in htmlBody
- The signature already contains full name/title, so don't duplicate "Ahmed" in the closing

## Follow-up Commands

### Mark as Read
```
Mark the following emails as read:
- ID: [messageId1]
- ID: [messageId2]
- ID: [messageId3]
```

### Batch Operations
```
Please perform these batch operations:
1. Mark all financial emails as read: [ID1, ID2, ID3]
2. Archive all promotional emails: [ID4, ID5]
3. Label meeting invites with "Calendar": [ID6, ID7]
```

### Search Specific Senders
```
Show me unread emails from [sender@email.com] in the last 7 days
```

### Thread Operations
```
Show me the full thread for Thread ID: [threadId]
Mark entire thread [threadId] as read
```

## Draft Email Management

After reading emails, Claude should:
1. **Create draft replies** for emails requiring responses
2. **Save drafts in correct threads** using threadId
3. **Ask for review** before sending any emails
4. **Always include professional signature** - Use HTML format with Merakey logo
5. **Provide draft IDs** for tracking

Example workflow:
- Read important emails
- Create draft replies and save to threads
- Report: "Draft created with ID: r123456789 - please review before sending"

## Token Efficiency Best Practices

1. **Batch tool calls** - Use multiple tool calls in single messages
2. **Limit email length** - Keep email bodies under 1000 characters when possible
3. **Use HTML format** - Always use HTML for professional appearance
4. **Skip redundant content** - Don't read duplicate emails in same thread
5. **Prioritize recent emails** - Focus on last 7 days unless specified otherwise

## Notion Query Efficiency

1. **Batch project searches** - Search for multiple keywords in single query
2. **Limit project page reads** - Only read full pages for high-priority matches
3. **Use project summaries** - Focus on status, timeline, and stakeholder sections
4. **Cache project info** - Store frequently accessed project details for session
5. **Selective retrieval** - Only fetch project details when email has clear business relevance

## Efficiency Tips

1. **Always use batch operations** when marking multiple emails as read
2. **Use specific date ranges** to minimize token usage
3. **Skip email content retrieval** for obvious spam/marketing
4. **Group similar actions** (e.g., mark all invoice emails as read together)

## Example Follow-up Workflow

```
User: Give me my email summary
Claude: [Provides structured summary with IDs]

User: Mark emails 196edad436c34c1b, 1970d2c2fb976be4, and 1970cd0281457955 as read
Claude: [Batch marks as read]

User: Archive the promotional email from Amanda Davis
Claude: [Archives email ID 1970d2c2fb976be4]

User: Create a "Needs Response" label and apply it to the RHPA training email
Claude: [Creates label and applies to email ID 1970d2473ae98f6c]
```

## Custom Filters

### Financial Only
```
Show me only unread financial/invoice emails from the last 7 days
Search: is:unread is:important after:[date] (invoice OR payment OR "amount due")
```

### Meeting Invites Only
```
Show me only unread meeting invitations from the last 7 days
Search: is:unread is:important after:[date] (invite OR meeting OR "calendar" OR "join")
```

### Urgent Only
```
Show me urgent unread emails from the last 24 hours
Search: is:unread is:important after:[yesterday] (urgent OR ASAP OR "action required")
```

### High Priority Business Only
```
Show me only high-priority business emails from the last 7 days
Search: is:unread is:important after:[date] (Vita OR MYHC OR Seamless OR Bell OR Westmount OR quote OR contract OR integration)
```

## Common Issues & Solutions

### Email Truncation (showing "...")
- **Cause:** Email body too long for Gmail MCP server
- **Solution:** Keep emails under 1000 characters, use HTML format
- **Fix:** Rewrite email more concisely with proper HTML formatting

### Emails Still Show Unread
- **Cause:** Multiple emails in thread, only some marked as read
- **Solution:** Check thread for additional unread emails
- **Action:** Use search to verify: `is:unread is:important after:[date]`

### Too Many Unimportant Emails
- **Cause:** Gmail not properly marking emails as important
- **Solution:** Focus only on `is:important` filter, skip promotional content
- **Action:** Train Gmail's importance markers by manually marking business emails as important

### Auto-Replies vs Real Responses
- **Distinguish:** Auto-replies often contain "automatic reply" or standard templates
- **Action:** Mark pure acknowledgment auto-replies as read, keep informative ones

## New Project Detection & Creation

Flag emails that may require new projects:
- New client inquiries with scope discussions
- Integration requests from unknown companies
- Budget/quote requests for undefined work
- Meeting requests for "discovery" or "requirements"
- Account transfers or service migrations

### Auto-Project Creation Criteria
If email contains:
- Quote request + scope definition + timeline
- New client + technical requirements
- Budget discussion + implementation plan
- Service transfer with multiple stakeholders
- Suggest creating new Notion project page with initial stakeholders and scope

## External Integration

When encountering property management emails:
- **Reference Notion page:** Golden Meadows Property Management for context
- **Cross-reference tasks:** Check existing todo items and priorities
- **Update tracking:** Note completed actions (repairs, payments, contacts)

When encountering business development emails:
- **Search for existing client projects** in Notion database
- **Link to ongoing negotiations** or implementation projects
- **Track stakeholder communication** and decision timelines
- **Note budget/scope changes** that affect project planning