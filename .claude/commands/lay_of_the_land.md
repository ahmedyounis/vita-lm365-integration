# Unified dashboard combining projects, emails, and calendar ex: `--standard` | `--focus --critical` | `--project MYHC --full` | `--optimize`

$ARGUMENTS

## Smart Integration Strategy:

Based on the provided arguments, execute the appropriate combination of focused commands and synthesize results:

### Command Execution Plan:

1. **Always Execute (Core Data):**
   - Gather project data using the projects command logic
   - Collect critical emails using the email command logic  
   - Fetch today's calendar using the calendar command logic

2. **Mode-Based Enhancement:**
   - If `--standard` flag: Get standard mode data from all three sources
   - If `--full` flag: Get full mode data from all three sources
   - If `--focus` flag: Focus on next 24 hours across all sources
   - If `--critical` flag: Show only urgent/blocking items from all sources

3. **Smart Filtering:**
   - If `--project <Name>` specified: Filter all data sources for that project
   - If `--today` flag: Limit all data to today's scope
   - If `--financial` flag: Extract financial items from all sources
   - If `--optimize` flag: Include optimization suggestions across workflows

## Integration Logic:

### Cross-Reference Analysis:
- **Project ↔ Email:** Match stakeholder names, project keywords
- **Project ↔ Calendar:** Match project names in meeting titles/descriptions  
- **Email ↔ Calendar:** Connect meeting invites with email discussions
- **All ↔ Blockers:** Identify dependencies across all three systems

### Priority Synthesis:
```
CRITICAL (🔥): 
- Overdue projects with meetings today
- Emails from project stakeholders blocking progress
- Meetings requiring prep with missing materials

URGENT (⚡):
- Projects due this week with pending emails
- Time-sensitive emails about active projects
- Meetings today affecting project timelines

IMPORTANT (📋):
- Active projects progressing normally
- Regular communication and updates
- Scheduled reviews and check-ins
```

### Output Format:

**Quick Mode (Default):**
```
## 🎯 EXECUTIVE DASHBOARD - [Date]

⚡ CRITICAL ACTIONS (Next 4 Hours)
[Cross-referenced urgent items from all sources]

📊 PROJECT HEALTH
[Project status with email/calendar indicators]

📧 INBOX PRIORITIES  
[Project-critical emails only]

📅 SCHEDULE LOAD
[Meeting impact on project work]
```

**Standard Mode:**
```
## 🌐 INTEGRATED WORKFLOW DASHBOARD

### 🔄 Active Context Map
[Visual connections between projects, emails, meetings]

### 🎯 TODAY'S INTEGRATED PLAN
[Time-blocked schedule with project context]

### 📊 CROSS-TOOL INSIGHTS
[Bottlenecks and optimization opportunities]
```

**Full Mode:**
[All Standard content plus:]
```
### 🧠 PATTERN ANALYSIS
[Velocity trends, communication patterns, meeting effectiveness]

### 🎯 STRATEGIC RECOMMENDATIONS
[Weekly and monthly optimization suggestions]

### 🤖 AUTOMATION OPPORTUNITIES
[Workflow improvements and efficiency gains]
```

## Intelligent Orchestration:

1. **Execute underlying command logic** for projects, emails, and calendar
2. **Cross-reference the results** to find connections and conflicts
3. **Prioritize items** based on combined impact scores
4. **Synthesize into unified view** with visual indicators
5. **Provide actionable insights** across all three domains
6. **Suggest optimizations** for workflow improvements

## Smart Features:

- **Conflict Detection:** Identify double-bookings, competing priorities
- **Preparation Alerts:** Flag meetings needing prep with missing materials  
- **Blocker Identification:** Highlight emails/meetings blocking project progress
- **Context Switching Optimization:** Group similar activities for efficiency
- **Timeline Correlation:** Show how today's activities affect project deadlines

This approach treats `lay_of_the_land` as an intelligent coordinator that leverages the specialized logic of each focused command while adding the unique value of cross-system analysis and unified prioritization.