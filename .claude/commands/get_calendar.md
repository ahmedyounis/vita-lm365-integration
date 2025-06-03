# Context-aware calendar intelligence with project and preparation insights. ex: `--standard` | `--prep` | `--project RHPA` | `--needs-prep` | `--focus`

$ARGUMENTS

## Command Modes:
- If `--standard` flag is present, provide project-aware weekly view (5-7 seconds)
- If `--full` flag is present, provide complete context with correlations (10-15 seconds)
- If `--prep` flag is present, show meeting preparation checklist
- If `--focus` flag is present, show best focus time blocks
- If `--project <Name>` is specified, show meetings for specific project
- If `--attendee <email>` is provided, filter by specific attendee
- If `--type <client|internal>` is specified, filter by meeting type
- If `--needs-prep` flag is present, show meetings requiring preparation
- If no flags are provided, use Quick Mode (today + critical meetings, 2-3 seconds)

## Step 1: Smart Meeting Categorization

### Meeting Priority Tiers:
1. **🔥 Project-Critical** - Directly impacts active projects
2. **💰 Client/Revenue** - External meetings affecting business
3. **🎯 Strategic** - Planning, reviews, decision meetings
4. **👥 Team/Operational** - Internal coordination
5. **📚 Learning/Optional** - Training, webinars, optional

### Context Extraction:
For each meeting, identify:
- Related Notion projects
- Email threads discussing agenda
- Required preparation documents
- Previous meeting notes/actions
- Stakeholder importance scores

## Step 2: Progressive Output

### Quick Mode (Default):
```
## 📅 CALENDAR INTELLIGENCE - NEXT 48 HOURS

⏰ TODAY (May 29)
├─ 2:00 PM: Vita RHPA API Meeting 🔥
│  └─ ⚠️ Review API requirements doc
│  └─ 📋 Links to RHPA Training project (85% complete)
├─ 4:30 PM: Quick sync with Khalid
│  └─ 📧 Re: MYHC infrastructure decision
└─ 5:00 PM: Focus block (protected)

🔔 TOMORROW (May 30)
├─ 10:00 AM: Baker Tilly payment reminder 💰
├─ 11:00 AM: Team standup
└─ 2:00 PM: Healex design review
   └─ 📎 Prepare mockups

Type 'calendar:get_calendar --standard' for weekly view
```

### Standard Mode:
```
## 📅 WEEKLY CALENDAR DASHBOARD

### Calendar Heatmap (Next 7 Days)
Mon │ Tue │ Wed │ Thu │ Fri │ Sat │ Sun
────┼─────┼─────┼─────┼─────┼─────┼────
 ▓▓▓ │ ▓▓░ │ ▓▓▓ │ ░░░ │ ▓▓░ │ ░░░ │ ░░░
 4hr │ 3hr │ 5hr │ 1hr │ 3hr │ 0hr │ 0hr

### 🔥 PROJECT-CRITICAL MEETINGS

**1. Vita RHPA API Integration Review**
- **Time:** Today 2:00-3:00 PM EST
- **Project Impact:** 🚨 HIGH (Blocks training rollout)
- **Related Project:** RHPA Training Platform (85% complete)
- **Key Stakeholders:** Vita (VP Training), Dev team
- **Preparation Score:** 3/5 ⚠️
  ├─ ✅ API documentation reviewed
  ├─ ✅ Test environment ready
  ├─ ⚠️ Integration examples needed
  ├─ ❌ Performance benchmarks missing
  └─ ❌ Fallback plan undefined
- **🤖 Pre-meeting Checklist:**
  1. Review API rate limits in doc
  2. Prepare 3 integration approaches
  3. Draft timeline for implementation

### 💰 CLIENT/REVENUE MEETINGS

[Similar detailed format for each category]

### 📊 Meeting Analytics:
- **Focus Time:** 40% (↓ from last week's 55%)
- **Meeting Heavy Days:** Wed (5hrs), Mon (4hrs)
- **Best Focus Blocks:** Thu AM, Fri PM
- **Double-booked:** None this week ✅
```

### Full Mode:
```
[Includes all Standard content plus:]

### 🔗 MEETING-PROJECT CORRELATIONS

Vita RHPA Meeting → RHPA Training Project → June 3 Deadline
├─ 📧 Email thread: "API Integration Questions" (3 messages)
├─ 📋 Notion tasks: 4 pending items related to meeting
├─ 💡 SUGGESTION: Block 2 hours after for implementation
└─ 🔔 ALERT: This unblocks final 15% of project

### 📈 MEETING PATTERNS & INSIGHTS

Vita Meeting History:
├─ Typical duration: 45-60 min (plan for full hour)
├─ Common topics: Technical barriers, timeline updates
├─ Decision style: Needs visual aids, prefers options
└─ Follow-up rate: 80% require immediate action

### 🎯 OPTIMIZATION OPPORTUNITIES

1. **Batch Similar Meetings:**
   - Move 3 check-ins to single afternoon
   - Save 90 minutes of context switching

2. **Protect Focus Time:**
   - Thursday AM completely free
   - Ideal for deep work on Google Contacts MCP

3. **Meeting Prep Blocks:**
   - Add 15-min prep before client meetings
   - Current gap: Vita meeting has no prep time
```

### Prep Mode:
```
## 📋 MEETING PREPARATION CHECKLIST

### Today's Critical Prep (By Priority):

🔥 **Vita RHPA Meeting (2:00 PM) - 90 min until start**

Prep Status: 3/8 items ⚠️ BEHIND SCHEDULE

✅ Completed:
├─ API documentation downloaded
├─ Test credentials verified
└─ Meeting agenda reviewed

⏳ In Progress:
├─ Setting up demo environment (50% done)
└─ Reviewing integration examples

❌ Not Started:
├─ Performance benchmark report
├─ Backup plan documentation  
└─ Questions list for Vita

📎 Required Documents:
├─ [Open] API Integration Guide v2.3
├─ [Missing] Performance benchmarks
└─ [Create] Implementation timeline

💡 Smart Suggestions:
1. Use existing Seamless Care integration as template
2. Prepare 3-slide visual for options
3. Block 2 hours post-meeting for notes
4. Set reminder to send follow-up by 5 PM
```

## Step 3: Intelligent Preparation

### Auto-Prep Detection:
For each meeting, analyze:
1. **Email threads** mentioning meeting topics
2. **Project tasks** due before/after meeting
3. **Previous meeting notes** for recurring meetings
4. **Stakeholder context** from communication patterns
5. **Required documents** from descriptions/agendas

### Preparation Scoring:
```
Score = (Documents Ready * 30%) + 
        (Agenda Clarity * 25%) +
        (Context Loaded * 25%) +
        (Time Allocated * 20%)
```

### Auto-Suggestions:
```
IF preparation_score < 50%:
  AND meeting_in < 2 hours:
    THEN flag as "🚨 URGENT PREP NEEDED"
    AND suggest specific actions
    AND estimate time required
```

## Step 4: Cross-Tool Intelligence

### Email Integration:
- Link meeting invites to email threads
- Extract action items from related emails  
- Identify pre-meeting questions
- Flag unanswered concerns

### Project Integration:
- Connect meetings to Notion projects
- Show project completion impact
- Highlight blocking dependencies
- Suggest post-meeting updates

### Todo Integration:
- Surface related todo items
- Create pre-meeting checklist
- Generate post-meeting actions
- Track meeting outcome items

## Step 5: Time Optimization

### Focus Time Protection:
```
Analyze calendar for:
- Fragmented days (many short gaps)
- Back-to-back meeting chains
- Insufficient prep/transition time
- Missing lunch/break blocks
```

### Meeting Efficiency Metrics:
```
- Average meeting duration vs. scheduled
- Recurring meeting effectiveness
- Client vs. internal time ratio
- Focus time percentage
```

### Smart Scheduling:
```
When creating new meetings:
1. Check project deadlines
2. Analyze attendee patterns
3. Protect existing focus blocks
4. Batch similar meeting types
5. Add automated prep time
```

## Output Commands:

### Quick Actions:
- `calendar:get_calendar` - Today's critical meetings (default)
- `calendar:get_calendar --standard` - Weekly dashboard view
- `calendar:get_calendar --full` - Complete analysis with insights
- `calendar:get_calendar --prep` - Preparation checklist mode
- `calendar:get_calendar --focus` - Find focus time blocks

### Filters:
- `--project="RHPA"` - Meetings for specific project
- `--attendee="vita@example.com"` - Meetings with specific person
- `--type=client` - Client meetings only
- `--needs-prep` - Meetings requiring preparation

### Smart Searches:
- `--conflicts` - Show double-booked times
- `--optimize` - Suggest schedule improvements  
- `--batch-similar` - Group similar meetings
- `--prep-time` - Add prep blocks to meetings

## Meeting Intelligence Features:

### Pattern Recognition:
```
Track for each stakeholder:
- Typical meeting duration
- Preferred meeting times
- Communication style
- Decision-making patterns
- Follow-up requirements
```

### Auto-Categorization:
```
Based on:
- Attendee list → Client/Internal/Mixed
- Title keywords → Project/Review/Planning
- Duration → Quick sync/Working session/Review
- Recurrence → Regular/Ad-hoc
- Description → Prep requirements
```

### Preparation Templates:
```
For each meeting type:
- Client Demo: Tech setup, slides, backup plan
- Project Review: Status update, blockers, next steps
- 1:1 Check-in: Topics list, feedback, goals
- Team Planning: Agenda, priorities, assignments
```

## Error Handling:

### Calendar Conflicts:
```
⚠️ DOUBLE-BOOKED: 2:00 PM Tuesday
- Meeting 1: Vita RHPA Review (accepted)
- Meeting 2: Healex Check-in (tentative)
Suggestion: Reschedule Healex to 3:30 PM (slot available)
```

### Missing Information:
```
⚠️ Meeting "Project Sync" missing:
- No agenda provided
- No project linkage found
- Unknown attendees' roles
Action: Request agenda from organizer
```

## Performance Optimization:

1. **Cache meeting patterns** for 24 hours
2. **Batch calendar API calls** by time range
3. **Progressive detail loading** (basic first, then enhance)
4. **Skip past meetings** unless analyzing patterns
5. **Limit attendee details** to key stakeholders

## Follow-up Commands:

### Create Smart Blocks:
```
Block prep time before all client meetings
Add 30-min buffers between back-to-back meetings
Protect Monday mornings for planning
```

### Meeting Analytics:
```
Show meeting time breakdown by project
Analyze meeting effectiveness (outcomes vs. time)
Identify redundant recurring meetings
```

### Bulk Optimization:
```
Optimize next week's schedule for focus time
Batch all check-ins to Tuesday afternoon
Add prep time to all external meetings
```

## Integration with Projects & Email:

### Pre-Meeting Intelligence:
```
For [meetingId], show:
- Related email threads
- Open project tasks
- Previous meeting notes
- Stakeholder context
```

### Post-Meeting Automation:
```
After [meetingId]:
- Create todo items from decisions
- Update project status in Notion
- Draft follow-up email
- Schedule next check-in
```

### Weekly Planning:
```
Generate weekly plan combining:
- Calendar commitments
- Project deadlines
- Email action items
- Focus time needs
```