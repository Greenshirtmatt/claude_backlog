# Product Backlog Gap Analysis Workflow

This repository helps product managers identify gaps between their Product Requirements Document (PRD) and their actual backlog of stories in Jira or Linear. It provides templates and a structured workflow to ensure comprehensive coverage of product requirements.

> **Note on Methodology**: This workflow is designed to support agile development practices, not waterfall processes. Rather than creating all stories upfront, use this approach iteratively: identify gaps, prioritize what matters now, create stories as needed, and repeat. The goal is continuous alignment between your PRD and backlog as priorities evolve and you respond to change.

## Prerequisites

- Active Jira or Linear project with existing stories
- Product Requirements Document (PRD) defining your product features
- Claude Code or another LLM with MCP (Model Context Protocol) support

## Getting Started

### Step 1: Set Up MCP Server Connection

Before you can read stories from your backlog system, you need to establish an MCP server connection:

**For Jira:**
- Configure the Jira MCP server with your instance URL and credentials
- Ensure the MCP server has read/write permissions for your project

**For Linear:**
- Configure the Linear MCP server with your API key
- Verify access to your team's issues and projects

**Testing the Connection:**
```
Ask your LLM: "Can you list the first 5 stories from [YOUR_PROJECT_KEY]?"
```

If the connection is working, you should see stories returned.

### Step 2: Export All Stories to Repository

Once the MCP connection is established, export your backlog:

1. **Request a full story export:**
   ```
   "Please read all stories from [YOUR_PROJECT_KEY] and create an all-stories.md file
   with all story details including title, description, status, and key."
   ```

2. **Request an active stories export:**
   ```
   "Please create an active-stories.md file with only stories in status:
   To Do, In Progress, or Backlog (exclude Resolved and Closed)."
   ```

**Expected Files:**
- `all-stories.md` - Complete story list for reference
- `active-stories.md` - Filtered view of active work

### Step 3: Add Your PRD to the Repository

1. Convert your PRD to Markdown format if it isn't already
2. Save it in the repository root (e.g., `prd.md` or `product-requirements.md`)
3. Ensure the PRD has line numbers or clear section headers for easy referencing

**PRD Best Practices:**
- Use clear section headers for different features
- Number or structure requirements for easy citation
- Include acceptance criteria and success metrics where applicable

### Step 4: Create Your Milestones File

1. Copy the template:
   ```
   cp templates/milestones_template.csv milestones.csv
   ```

2. Customize with your actual product milestones:
   - Replace example milestones with your product features
   - Break down each milestone into specific objectives
   - Set realistic status values (Planned, In Design, In Progress, Completed)

**Example structure:**
```csv
Milestone,Objective,Status,
User Authentication,Implement OAuth2 login,In Progress,
,Add password reset flow,Planned,
,Enable 2FA,Planned,
,,
Payment Processing,Integrate Stripe API,Completed,
,Build subscription management,In Progress,
```

### Step 5: Generate Gap Analysis

Ask your LLM to perform the gap analysis:

```
"Please analyze my milestones.csv against active-stories.md and identify
gaps where milestone objectives don't have corresponding JIRA stories.
Create a gap-analysis.md file with:
1. Each milestone and its objectives
2. Which stories cover each objective (if any)
3. Missing stories needed to complete objectives
4. Priority level for each gap (High, Medium, Low)"
```

**Expected Output:**
- `gap-analysis.md` - Comprehensive mapping of milestones to stories with identified gaps

### Step 6: Review and Prioritize Gaps

1. Open `gap-analysis.md` and review the identified gaps
2. Focus on High priority gaps first
3. Validate that the gaps are real (sometimes existing stories may cover objectives implicitly)
4. Decide which gaps to address in your current planning cycle

### Step 7: Draft New Stories

For each gap you want to address:

1. **Request detailed story analysis:**
   ```
   "For the gap '[OBJECTIVE NAME]', please review the PRD and create a detailed
   story recommendation in prd-findings-priority-stories.md including:
   - PRD line references
   - Recommended acceptance criteria
   - Technical considerations"
   ```

2. **Review the draft** and provide feedback:
   - Adjust scope or acceptance criteria
   - Add missing context or requirements
   - Confirm technical approach

### Step 8: Create Stories in Jira/Linear

Once you've finalized the story details:

1. **Update the Jira template:**
   ```
   Edit templates/jira-story-template.json with your:
   - Project key
   - Component name
   - Default assignee
   - Epic links (if applicable)
   ```

2. **Create the story:**
   ```
   "Please create a JIRA story for [OBJECTIVE NAME] using the details from
   prd-findings-priority-stories.md and the defaults from jira-story-template.json"
   ```

3. **Verify creation:**
   - Confirm the story was created successfully
   - Note the story key (e.g., PROJ-123)
   - Review in Jira/Linear to ensure formatting is correct

4. **Update tracking:**
   ```
   "Please update active-stories.md with the newly created story"
   ```

### Step 9: Iterate

After creating stories, continue the cycle:

1. Re-run gap analysis to see remaining gaps
2. Update milestones.csv as priorities shift
3. Periodically refresh active-stories.md from Jira/Linear
4. Keep gap-analysis.md current with latest backlog state

## Repository Files

### Your Working Files
- **PRD** (e.g., `prd.md`) - Product requirements document
- **milestones.csv** - High-level product milestones and objectives
- **active-stories.md** - Current backlog (To Do, In Progress, Backlog)
- **all-stories.md** - Complete story archive for reference
- **gap-analysis.md** - Analysis of gaps between milestones and backlog
- **prd-findings-priority-stories.md** - Detailed recommendations for priority gaps

### Templates (in `/templates/`)
- **jira-story-template.json** - Default values for story creation
- **milestones_template.csv** - Example milestone structure
- **instructions_template.md** - Detailed workflow documentation
- **MILESTONES_TEMPLATE_README.md** - Milestones CSV documentation

### Guidance Files
- **CLAUDE.md** - Instructions for LLM assistance in this repo
- **README.md** - This file

## Tips for Success

1. **Keep active-stories.md fresh**: Re-export weekly to catch new stories and status changes
2. **Reference PRD line numbers**: Always cite specific lines when creating stories
3. **Update milestones regularly**: Adjust objectives as product priorities evolve
4. **Review gap analysis frequently**: Use it in sprint planning to ensure PRD coverage
5. **Maintain story quality**: Use the template format consistently for all story descriptions

## Common Workflows

### Weekly Planning Session
1. Refresh `active-stories.md` from Jira/Linear
2. Update `milestones.csv` with latest status
3. Regenerate `gap-analysis.md`
4. Identify 2-3 high-priority gaps to address
5. Draft and create new stories

### PRD Updates
1. Update your PRD markdown file
2. Review `milestones.csv` - do objectives still align?
3. Regenerate `gap-analysis.md` to identify new gaps
4. Create stories for any new requirements

### Sprint Planning
1. Review `gap-analysis.md` to identify critical missing stories
2. Draft stories for gaps that block upcoming milestones
3. Create stories in Jira/Linear before sprint planning meeting
4. Use milestone completion status to inform sprint goals

## Troubleshooting

**MCP connection not working?**
- Verify your API credentials or authentication tokens
- Check MCP server configuration
- Ensure network access to Jira/Linear instance

**Story export is incomplete?**
- Check project permissions
- Verify JQL query or Linear filters aren't too restrictive
- Try exporting smaller batches (e.g., by status or component)

**Gap analysis shows false positives?**
- Update story descriptions to better match milestone objectives
- Adjust milestone objectives to be more specific
- Use notes in gap-analysis.md to document intentional decisions

**Story creation fails?**
- Verify required fields in jira-story-template.json
- Check that components and epic links exist in your project
- Ensure assignee username is correct

## Support

For issues with this repository structure or templates, review:
- `CLAUDE.md` for LLM-specific guidance
- `templates/instructions_template.md` for detailed conventions
- `templates/MILESTONES_TEMPLATE_README.md` for CSV format help
