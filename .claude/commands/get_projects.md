# Smart project dashboard with progressive detail and visual timeline. ex: `--standard` | `--full --project MYHC` | `--focus --overdue` | `--priority high`

$ARGUMENTS

## Command Modes:
- If `--standard` flag is present, provide balanced detail with timeline view (5-7 seconds)
- If `--full` flag is present, provide complete analysis with dependencies (10-15 seconds)  
- If `--focus` flag is present, show only next 7 days
- If `--project <Name>` is specified, focus on that specific project only
- If `--priority <Level>` is provided, filter by priority level (high/medium/low)
- If `--overdue` flag is present, show only overdue projects
- If `--due-week <N>` is specified, show projects due within N weeks
- If no flags are provided, use Quick Mode (2-3 seconds, key info only)

## Step 1: Initial Project Query

Use the Notion MCP server to retrieve "In Progress" projects efficiently:

1. Query the Notion Projects database
2. Filter for Status = "In Progress"
3. Sort by: Priority (High → Medium → Low), then Due Date (ascending)
4. Limit initial fetch to minimize API calls

## Step 2: Progressive Loading

### Quick Mode Output (Default):

```
## 🚀 PROJECT SNAPSHOT (Last updated: [timestamp])

🔴 CRITICAL (Overdue/Blocked)
└─ MYHC Migration: 78% ████████░░ ⚠️ Awaiting Khalid response

🟡 ATTENTION (Due This Week)  
├─ Telnyx Review: 90% █████████░ 📅 May 30
├─ Midos Birthday: 60% ██████░░░░ 📅 May 31
└─ Vita RHPA: 85% ████████░░ 📅 June 3

🟢 ON TRACK (Progressing Well)
├─ Google Contacts MCP: 65% ██████░░░░ 📅 June 7
└─ Healex Website: 25% ██░░░░░░░░ 📅 June 12

⚪ FUTURE (Not Urgent)
└─ Personal Finance: 10% █░░░░░░░░░ 📅 June 15

Type 'project:get_projects --standard' for timeline view
```

### Standard Mode Output:

```
## 📊 PROJECT TIMELINE DASHBOARD

### Timeline View (Next 30 Days)
May 29  │  June 5  │  June 12  │  June 19  │  June 26
════════│══════════│═══════════│═══════════│══════════
MYHC Migration    ████████████▓░░░░░░░░░  78% │ ⚠️ OVERDUE
Telnyx Review     ███████████▓░░░░░░░░░░  90% │ 📅 May 30
Vita RHPA         ░░██████████████▓░░░░░  85% │ 📅 June 3
Google Contacts   ░░░░███████████████▓░░  65% │ 📅 June 7
Healex Website    ░░░░░░░░░░░░█████████▓  25% │ 📅 June 12

Legend: ███ Complete ▓▓▓ Current ░░░ Planned

### 🎯 IMMEDIATE ACTIONS (Top 3)

1. **Follow up with Khalid** - MYHC Migration
   └─ Email sent 4 hours ago, blocks 22% of project

2. **Complete Telnyx review** - Due Tomorrow
   └─ Form link: https://forms.gle/KqBEjLK4AqVYoVPP6

3. **Prepare for Vita meeting** - Today 2 PM
   └─ Review API requirements and blockers
```

### Full Mode Output (includes everything):

```
## 📊 COMPREHENSIVE PROJECT INTELLIGENCE

[Include all Standard Mode content, plus:]

### 🎯 PROJECT DEEP DIVE

**🏢 MYHC Migration to Khalid** (Project #169) │ 78% Complete │ ⚠️ OVERDUE
┌─ 🎯 **GOAL:** Complete account transfer for independent operations
├─ 💰 **BUDGET:** $0 (internal) │ ⏱️ **TIME:** 12 hours invested
├─ 👥 **STAKEHOLDERS:** Khalid, Helen, Hollie, Andrew
└─ 🚨 **CRITICAL PATH:** Google Drive → Bell Internet → Complete

📋 **GRANULAR TASKS:**
├─ ✅ AWS user creation (khalid - systemAdmin) - May 28
├─ ✅ 407 ETR phone transfer - May 28  
├─ ✅ Bitwarden ownership transfer - May 27
├─ ✅ GitHub admin access (kmyounis) - May 27
├─ ⏳ **BLOCKING:** Google Drive decision pending
│   └─ 📧 Status email sent May 29 08:44
├─ ⏳ **NEXT:** Bell Internet portal transfer
│   └─ 👤 Coordinate with Hollie for form
└─ 📈 **METRICS:** 7/9 accounts transferred

### 📈 PROJECT HEALTH MATRIX

PROJECT          │ PROGRESS │ HEALTH  │ MOMENTUM │ RISK
═════════════════│══════════│═════════│══════════│═════════
MYHC Migration   │ ████░░ 78%│ 🟡 WAIT │ ⬇️ SLOW  │ 🟡 MED
Vita RHPA        │ ████░░ 85%│ 🟢 GOOD │ ⬆️ FAST  │ 🟢 LOW
Google Contacts  │ ███░░░ 65%│ 🟢 GOOD │ ➡️ STEADY│ 🟢 LOW

### 🔗 DEPENDENCIES & BLOCKERS

MYHC Migration:
└─ BLOCKED BY: Khalid infrastructure decision
   └─ BLOCKS: Business continuity for MYHC

Vita RHPA Training:
└─ DEPENDS ON: LM365 API access
   └─ BLOCKS: Training content migration
```

### Focus Mode Output (Next 7 Days Only):

```
## 🎯 FOCUS: Next 7 Days

TODAY (May 29)
├─ ⏰ 2:00 PM: Vita RHPA meeting (prep API requirements)
└─ 📧 Follow up: Khalid MYHC response (blocks project)

TOMORROW (May 30)  
├─ 💰 Pay: Baker Tilly $390 (10 AM reminder set)
└─ ✍️ Complete: Telnyx review for $75 credit

THIS WEEK
├─ May 31: Midos Birthday planning
├─ June 1: MYHC invoice prep
└─ June 3: Vita RHPA deadline
```

## Step 3: Project Categorization

Automatically categorize projects by:

### Business Area:
- 💻 **Technical Development** (Google Contacts MCP, Personal Finance)
- 💰 **Financial & Business** (Telnyx Review, MYHC Invoice)
- 🏢 **Client Projects** (Vita RHPA, MYHC Migration)
- 🏠 **Property Management** (Golden Meadows)
- 📈 **Business Operations** (Merakey Operations)
- 🌐 **Web Development** (Healex Website)
- 🎉 **Personal** (Midos Birthday)

### Priority Matrix:
- 🔴 **CRITICAL:** Overdue or blocking other work
- 🟡 **ATTENTION:** Due within 7 days
- 🟢 **ON TRACK:** Progressing normally
- ⚪ **FUTURE:** Due beyond 7 days

## Step 4: Action Intelligence

For each project, extract and prioritize:

1. **Immediate Actions** (next 4 hours)
2. **Today's Tasks** (next 24 hours)
3. **This Week** (next 7 days)
4. **Blockers & Dependencies**
5. **Success Metrics & Goals**

## Step 5: Smart Suggestions

Based on project analysis, provide:

### Workflow Optimization:
- Batch similar tasks across projects
- Identify optimal work sequences
- Suggest meeting preparations
- Flag deadline conflicts

### Risk Mitigation:
- Highlight blockers affecting multiple projects
- Suggest escalation triggers
- Identify resource conflicts
- Recommend contingency actions

## Output Commands:

### Quick Actions:
- `project:get_projects` - Quick snapshot (default)
- `project:get_projects --standard` - Timeline view
- `project:get_projects --full` - Complete analysis
- `project:get_projects --focus` - Next 7 days only
- `project:get_projects --project="MYHC"` - Single project deep dive

### Filters:
- `--priority=high` - High priority only
- `--overdue` - Overdue projects only
- `--due-week` - Due within 7 days
- `--category=technical` - By category

## Error Handling:

### API Rate Limits:
```
⚠️ Rate limit approaching. Showing cached data from [timestamp].
Refresh available in: 5 minutes
```

### Mobile/Narrow Display:
```
📱 Narrow display detected. 
Showing mobile-optimized view.
Use --desktop to force full width.
```

## Integration Notes:

- Cache project data for 15 minutes to reduce API calls
- Use progressive enhancement for visual elements
- Provide text-only fallback for accessibility
- Track project velocity between runs