# Intelligent email summaries with project awareness. ex: `--standard` | `--urgent --days 1` | `--project Vita` | `--sender khalid@example.com`

$ARGUMENTS

## Command Modes:
- If `--standard` flag is present, provide project-aware categorization (5-7 seconds)
- If `--full` flag is present, provide complete analysis with cross-references (10-15 seconds)
- If `--project <Name>` is specified, show only emails related to that project
- If `--sender <email>` is provided, filter by specific sender
- If `--days <N>` is specified, limit to emails from last N days
- If `--urgent` flag is present, show only urgent/time-sensitive emails
- If `--financial` flag is present, show only financial emails
- If no flags are provided, use Quick Mode (critical emails only, 2-3 seconds)

## Step 1: Intelligent Email Prioritization

### Priority Tiers:
1. **🔥 Project-Critical** - Affects active projects with deadlines
2. **⏰ Time-Sensitive** - Meetings today, payments due, urgent requests
3. **💰 Financial** - Invoices, payments, account alerts
4. **📋 Action Required** - Needs response but not urgent
5. **📧 FYI/Auto-Replies** - Informational only

### Smart Search Sequence:
```
1. Project-critical: is:unread is:important (Khalid OR Helen OR Vita OR MYHC OR "project update")
2. Time-sensitive: is:unread is:important (meeting OR urgent OR "due today" OR payment)
3. Financial: is:unread is:important (invoice OR payment OR "amount due" OR alert)
4. General important: is:unread is:important after:[7_days_ago]
5. Fallback: is:unread after:[7_days_ago] (if no important results)
```

## Step 2: Progressive Output

### Quick Mode (Default):
```
## 📧 CRITICAL EMAILS - ACTION REQUIRED

🔥 **PROJECT-CRITICAL (2)**
└─ Khalid: Re: MYHC Migration Infrastructure
   └─ 🚨 Blocks MYHC project (78% complete)
   └─ 💬 "Prefer Google Drive option for..."
   └─ ⚡ Action: Update project, proceed with migration

⏰ **TIME-SENSITIVE (1)**  
└─ Vita: Meeting Confirmation - Today 2 PM
   └─ 📅 Links to RHPA Training project
   └─ 📎 Attached: API requirements doc
   └─ ⚡ Action: Review doc before meeting

💰 **FINANCIAL (1)**
└─ Baker Tilly: Payment Confirmation
   └─ ✅ Payment 1 of 2 received
   └─ 📅 Reminder: $390 due tomorrow
   └─ ⚡ Action: None (informational)

Type 'email:get_emails --standard' for full categorization
```

### Standard Mode:
```
## 📧 EMAIL INTELLIGENCE DASHBOARD

### 📊 Email Overview
Total Unread: 15 | Important: 8 | Project-Related: 5

### 🔥 PROJECT-CRITICAL EMAILS

**1. MYHC Infrastructure Decision** 
- **ID:** msg123abc | **Thread:** thd456def
- **From:** Khalid Younis (khalid@westmountpharmacy.ca)
- **Received:** 30 minutes ago
- **Project Impact:** 🚨 CRITICAL (9/10)
- **Related Project:** MYHC Migration (78% complete, OVERDUE)
- **Summary:** Khalid prefers Google Drive option
  • Confirms Google Workspace is ready
  • Suggests Friday for migration window
  • Asks about data retention policy
- **Action Required:** Update project status, schedule migration
- **🤖 Draft Ready:** "Hi Khalid, Perfect! Friday works..."

### ⏰ TIME-SENSITIVE

[Similar detailed format for each category]

### 📌 Quick Actions:
- Mark project emails read: "Mark emails msg123abc, msg789ghi as read"
- Send Khalid draft: "Send draft reply to Khalid confirming Friday"
- Archive financials: "Archive Baker Tilly confirmation"
```

### Full Mode:
```
[Includes all Standard content plus:]

### 🔗 EMAIL-PROJECT CORRELATIONS

📧 Khalid Email → 📋 MYHC Migration → 📅 No meetings scheduled
└─ 🤖 SUGGESTION: Schedule Friday migration session
└─ 📊 IMPACT: Unblocks final 22% of project
└─ 🔔 ALERT: Update project timeline after confirmation

### 📈 COMMUNICATION PATTERNS

Khalid Response Pattern:
├─ Avg response time: 4.5 hours
├─ Prefers: Brief, bullet-pointed emails
└─ Best reach: Morning emails (9-11 AM)

### 🎯 WORKFLOW AUTOMATION

If Khalid confirms Google Drive:
1. ✅ Update MYHC project to 89% complete
2. 📧 Email Andrew with migration plan
3. 📅 Create calendar event for Friday
4. 📋 Add migration checklist to todos
5. 🔔 Set reminder for Thursday prep

### 📊 EMAIL METRICS

This Week's Pattern:
- Project emails: 45% (↑ from 30%)
- Financial: 20% (normal)
- Meetings: 15% (↓ from 25%)
- Auto-replies: 20% (normal)
```

## Step 3: Smart Features

### Auto-Draft Generation (Project-Critical Only):
```
For emails with Project Impact Score ≥ 8/10:
- Generate context-aware draft
- Include project status reference
- Suggest next steps
- Apply email signature
```

### Batch Operations:
```
Group similar emails for efficient processing:
- All invoice confirmations
- All meeting acceptances
- All project updates from same sender
```

### Relationship Intelligence:
```
Track for each key contact:
- Communication frequency
- Response patterns
- Project involvement
- Preferred communication style
```

## Step 4: Integration with Projects

### Project Keyword Extraction:
From each email, identify:
- Company names (Vita, MYHC, Seamless)
- Project references (migration, integration, training)
- Technical terms (API, database, portal)
- Deadlines and dates
- Budget/cost mentions

### Auto-Linking Logic:
```
IF email contains project keywords:
  AND sender is project stakeholder:
    THEN link email to project
    AND calculate impact score
    AND suggest project updates
```

## Step 5: Email Signature & Formatting

### Always Include for Drafts:
```html
<br><br>
<img src="https://drive.google.com/uc?export=view&id=1vfZgFtTwLvi3vII2k3CUZJIhrTmGl9pr" 
     alt="Ahmed Younis - Merakey" 
     style="width: 240px; height: auto; display: block;">
```

### HTML Email Format:
- Use `mimeType: "text/html"`
- Include both `body` and `htmlBody`
- Use `<strong>` for emphasis
- Use `<br>` for line breaks

## Output Commands:

### Quick Actions:
- `email:get_emails` - Critical emails only (default)
- `email:get_emails --standard` - Full categorization
- `email:get_emails --full` - Complete analysis
- `email:get_emails --project` - Project-related only
- `email:get_emails --financial` - Financial emails only

### Filters:
- `--sender="khalid@westmountpharmacy.ca"` - From specific sender
- `--days=1` - Last 24 hours only
- `--urgent` - Urgent/time-sensitive only
- `--unread-only` - Skip read emails in threads

## Error Handling:

### Email Truncation:
```
⚠️ Email body truncated. Showing first 1000 chars.
Use --full-content to retrieve complete email.
```

### Rate Limits:
```
⚠️ Gmail API limit approaching (80/100 requests).
Showing priority emails only. Reset in: 15 minutes.
```

## Performance Optimization:

1. **Cache sender patterns** for 24 hours
2. **Batch API calls** when marking read/archiving
3. **Skip thread duplicates** unless specified
4. **Limit initial search** to 15 results
5. **Progressive content loading** (headers first, then body)

## Follow-up Commands:

### Mark as Read:
```
Mark emails msg123abc, msg789ghi as read
```

### Batch Operations:
```
- Archive all financial confirmations
- Label project emails with "Active-Project"
- Mark thread thd456def as read
```

### Smart Searches:
```
- Show emails needing response today
- Show project blockers from last 48 hours
- Show financial emails pending action
```