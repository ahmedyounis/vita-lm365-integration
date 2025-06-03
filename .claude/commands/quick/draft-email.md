# Create professional email drafts with smart formatting

Examples: `--to user@example.com --subject "Topic" message` | `--formal --brief update text` | `--project MYHC status`

Email request: $ARGUMENTS

## Instructions:
- If the request contains "--to <email>" extract the recipient email address
- If the request contains "--subject <text>" use that as the subject line
- If the request contains "--project <name>" reference the project context
- If the request contains "--formal" use formal business tone
- If the request contains "--brief" keep the email concise (under 100 words)
- The remaining text should be treated as the main message or context

## Email Requirements:
1. **Professional Format**
   - Clear, descriptive subject line
   - Proper greeting and closing
   - Well-structured paragraphs
   - Professional but friendly tone

2. **Content Structure**
   - Brief introduction if needed
   - Main message or request clearly stated
   - Any necessary context or background
   - Clear next steps or call to action
   - Appropriate closing

3. **Standard Signature**
   - Always include Ahmed Younis signature
   - Use HTML format with proper styling
   - Include Merakey branding image

4. **Smart Context**
   - Reference any relevant project updates
   - Include appropriate urgency level
   - Suggest optimal send timing if relevant

Generate the email using `mcp__gmail__draft_email` with proper HTML formatting.