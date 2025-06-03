# Complete help for all custom commands with usage examples

Shows: Command syntax, examples, common patterns, workflow tips

## Core Dashboard Commands

### `/project:get_projects [flags]`
Smart project dashboard with progressive detail and visual timeline.

**Usage Examples:**
- `/project:get_projects` - Quick snapshot (default)
- `/project:get_projects --standard` - Timeline view with details
- `/project:get_projects --full` - Complete analysis with dependencies
- `/project:get_projects --focus` - Next 7 days only
- `/project:get_projects --project MYHC` - Focus on specific project
- `/project:get_projects --priority high --overdue` - High priority overdue projects

### `/project:get_emails [flags]`
Intelligent email summaries with project awareness.

**Usage Examples:**
- `/project:get_emails` - Critical emails only (default)
- `/project:get_emails --standard` - Project-aware categorization
- `/project:get_emails --full` - Complete analysis with cross-references
- `/project:get_emails --project Vita` - Emails related to Vita project
- `/project:get_emails --sender khalid@westmountpharmacy.ca` - From specific sender
- `/project:get_emails --urgent --days 1` - Urgent emails from last 24 hours

### `/project:get_calendar [flags]`
Context-aware calendar intelligence with project insights.

**Usage Examples:**
- `/project:get_calendar` - Today + critical meetings (default)
- `/project:get_calendar --standard` - Project-aware weekly view
- `/project:get_calendar --prep` - Meeting preparation checklist
- `/project:get_calendar --focus` - Best focus time blocks
- `/project:get_calendar --project RHPA` - Meetings for specific project
- `/project:get_calendar --needs-prep` - Meetings requiring preparation

### `/project:lay_of_the_land [flags]`
Unified dashboard combining projects, emails, and calendar.

**Usage Examples:**
- `/project:lay_of_the_land` - Critical items only (default)
- `/project:lay_of_the_land --standard` - Balanced view with correlations
- `/project:lay_of_the_land --full` - Complete analysis with insights
- `/project:lay_of_the_land --focus` - Next 24 hours only
- `/project:lay_of_the_land --critical` - Only blockers and urgent items
- `/project:lay_of_the_land --optimize` - Schedule improvement suggestions

## Quick Action Commands

### `/project:quick:draft-email <request>`
Create professional email drafts with smart formatting.

**Usage Examples:**
- `/project:quick:draft-email --to khalid@westmountpharmacy.ca --subject MYHC Migration Update --project MYHC Confirmed Google Drive approach, scheduling Friday migration`
- `/project:quick:draft-email --formal --brief Follow up on Vita API integration timeline`
- `/project:quick:draft-email Team meeting notes from today's RHPA discussion`

### `/project:quick:prep-meeting <meeting>`
Comprehensive meeting preparation with context and checklist.

**Usage Examples:**
- `/project:quick:prep-meeting Vita RHPA API Meeting`
- `/project:quick:prep-meeting --agenda Baker Tilly Review`
- `/project:quick:prep-meeting --docs --questions Client Design Review`

### `/project:quick:status-update <scope>`
Generate status updates for projects or timeframes.

**Usage Examples:**
- `/project:quick:status-update --project MYHC --client`
- `/project:quick:status-update --week --internal`
- `/project:quick:status-update --brief --month`

## Workflow Commands

### `/project:workflow:fix-issue <issue>`
Systematically analyze and fix issues or problems.

**Usage Examples:**
- `/project:workflow:fix-issue API integration failing on Vita RHPA platform`
- `/project:workflow:fix-issue Payment processing timeout on Healex website`
- `/project:workflow:fix-issue Database connection errors in production`

### `/project:workflow:automate <workflow>`
Design automation for repetitive tasks and workflows.

**Usage Examples:**
- `/project:workflow:automate --email Daily project status email to stakeholders`
- `/project:workflow:automate --calendar Weekly meeting prep and follow-up tasks`
- `/project:workflow:automate --daily Morning routine for project reviews`

## Command Syntax Guidelines

**Flag Format:**
- Use `--flag` for boolean options
- Use `--flag value` for parameters
- Use `--flag "multi word value"` for phrases

**Common Flags:**
- `--standard` - Balanced detail level
- `--full` - Complete analysis
- `--focus` - Time-focused view
- `--project <name>` - Filter by project
- `--brief` - Concise output
- `--urgent` - Priority filtering

**Examples of Multi-Flag Usage:**
```
/project:get_projects --standard --project MYHC --overdue
/project:get_emails --urgent --days 2 --project Vita
/project:lay_of_the_land --focus --critical --optimize
```

## Tips for Effective Command Usage

1. **Start Simple:** Use commands without flags first, then add filters
2. **Combine Flags:** Most commands support multiple flags for precise filtering
3. **Use Quotes:** Wrap multi-word values in quotes (`--project "Google Contacts"`)
4. **Chain Commands:** Use insights from one command to refine another
5. **Save Frequent Patterns:** Note your most-used flag combinations

## Common Workflows

**Morning Routine:**
1. `/project:lay_of_the_land --focus` - Check today's priorities
2. `/project:get_emails --urgent` - Handle critical emails
3. `/project:get_calendar --prep` - Prepare for meetings

**Project Deep Dive:**
1. `/project:get_projects --project <NAME> --full` - Complete project status
2. `/project:get_emails --project <NAME>` - Related communications
3. `/project:get_calendar --project <NAME>` - Project meetings

**End of Day:**
1. `/project:quick:status-update --brief` - Day's accomplishments
2. `/project:lay_of_the_land --tomorrow` - Tomorrow's plan
3. `/project:workflow:automate --daily` - Optimize routine