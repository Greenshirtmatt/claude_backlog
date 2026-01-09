# Active Stories Template README

## Overview

The Active Stories document provides a snapshot of all non-resolved JIRA stories for a specific component or project. This serves as a quick reference for team members to understand current work in progress, upcoming tasks, and backlog items without having to navigate through JIRA's interface.

## Purpose

**Why maintain an active stories document?**
- **Quick Reference**: Get a complete view of active work without opening JIRA
- **Status Meetings**: Perfect for sprint planning, standups, and team syncs
- **Context Sharing**: Easy to share with stakeholders who don't have JIRA access
- **Historical Record**: Snapshot in time for documentation purposes
- **Offline Access**: Review stories without internet connection
- **Pattern Recognition**: Spot trends in story types, assignments, and complexity

## Structure

### Header Information
- **Total Active Issues**: Count of stories included
- **Generated**: Date of export (important for knowing freshness)
- **Component**: Which component/product area these stories belong to
- **Note**: Clarifies which statuses are included/excluded

### Story Organization

Stories are grouped by status in priority order:
1. **In Progress** - Currently being worked on
2. **To Do** - Ready to start, usually in current or next sprint
3. **Backlog** - Prioritized but not scheduled yet

### Story Details

Each story includes:
- **Story ID**: JIRA ticket number (e.g., PROJ-101)
- **Title**: Brief summary of the work
- **Status**: Current state
- **Assignee**: Who's responsible
- **Created/Updated**: Timestamps for context
- **Story Points**: Complexity estimate (if set)
- **Description**: User story or detailed explanation
- **Notes**: Additional context, technical details, open questions
- **Acceptance Criteria**: Definition of done
- **Implementation Notes**: Technical approach, libraries, dependencies

### Summary Statistics

At the bottom, aggregate metrics provide quick insights:
- Count by status
- Count by assignee (top contributors)
- Story point totals

## How to Generate Active Stories Document

### Option 1: JIRA Export (Manual)

1. **Filter in JIRA**:
   ```
   project = PROJ
   AND component = "Your Component"
   AND status IN ("In Progress", "To Do", "Backlog")
   ORDER BY status DESC, updated DESC
   ```

2. **Export to CSV or JSON** from JIRA

3. **Convert to Markdown** using the template structure

4. **Add details**: Copy description, notes, and acceptance criteria for key stories

### Option 2: JIRA API (Automated)

Use JIRA's REST API to fetch stories and generate markdown:

```bash
# Example using jq for JSON processing
curl -u user:token 'https://your-jira.com/rest/api/2/search?jql=project=PROJ+AND+status+IN+(In+Progress,To+Do,Backlog)' \
  | jq -r '.issues[] | "### \(.key)\n**\(.fields.summary)**\n- Status: \(.fields.status.name)\n"'
```

Consider creating a script to automate this process.

### Option 3: JIRA Plugin

Some JIRA plugins can export to markdown format directly.

## Best Practices

### Do This
- ✅ **Regenerate regularly** - Weekly or before major meetings
- ✅ **Include key details** - Description and acceptance criteria for In Progress stories
- ✅ **Keep it current** - Update as stories move through workflow
- ✅ **Use consistent formatting** - Follow the template structure
- ✅ **Add context** - Notes and implementation details help future readers
- ✅ **Track story points** - Helps with velocity calculations

### Avoid This
- ❌ **Including resolved/closed stories** - This is for active work only
- ❌ **Too much detail** - Not every backlog story needs full description
- ❌ **Stale exports** - Document older than 1 week loses value
- ❌ **Inconsistent structure** - Makes it hard to scan
- ❌ **Missing metadata** - Always include generated date and component

## Detail Level Guidelines

**In Progress Stories (High Detail)**
- Full description
- Detailed acceptance criteria
- Implementation notes
- Open questions or blockers
- Design links if applicable

**To Do Stories (Medium Detail)**
- At minimum: title, status, assignee, story points
- Description for stories in next sprint
- Acceptance criteria if already defined

**Backlog Stories (Low Detail)**
- At minimum: title, status, assignee, story points
- Description only if story is well-defined
- Can be just the title for future scope items

## Use Cases

### Sprint Planning
- Review To Do and Backlog stories for sprint commitment
- Story point totals help with capacity planning
- Easily identify dependencies and blockers

### Daily Standup
- Quick reference for what each team member is working on
- Spot stories that haven't been updated recently
- Identify blockers mentioned in notes

### Stakeholder Updates
- Share with non-technical stakeholders without JIRA access
- Show progress by counting completed vs in-progress stories
- Demonstrate backlog prioritization

### Developer Onboarding
- New team members can review current and upcoming work
- Understand team's focus areas and priorities
- See examples of well-written stories

### Retrospectives
- Review patterns in story flow (how long in each status)
- Identify if certain story types get stuck
- Discuss if story points are accurate

## Integration with Other Documents

This document works alongside:
- **milestones.csv**: Maps stories to strategic objectives
- **gap-analysis.md**: Identifies objectives without stories
- **sprint-backlog.md**: Subset of To Do stories for current sprint
- **completed-stories.md**: Archive of resolved stories

## Customization Tips

**Adapt the template to your workflow:**

1. **Add custom fields** - Priority, Epic link, Sprint, Labels
2. **Change status groups** - Use your team's workflow states
3. **Different sorting** - Sort by priority, assignee, or epic
4. **Add visual indicators** - Use emojis or badges (🚨 for blocked stories)
5. **Include links** - Link to JIRA, Confluence, design docs
6. **Add estimates** - Include time estimates alongside story points

**Example customization:**

```markdown
### PROJ-101 🚨 BLOCKED
**Implement Authentication** [Epic: Security]
- **Status:** In Progress
- **Assignee:** John Smith
- **Priority:** P0
- **Sprint:** Sprint 23
- **Blocked By:** Waiting for security review
- **Story Points:** 5
```

## Automation Ideas

### Weekly Auto-Generation

Create a script that:
1. Fetches stories from JIRA API
2. Formats as markdown using template
3. Commits to repository
4. Sends notification to team channel

### Status Change Notifications

Hook into JIRA webhooks to:
- Update document when story status changes
- Notify team when story moves to "In Progress"
- Alert if story hasn't been updated in 5+ days

### Dashboard Integration

- Parse the markdown to generate web dashboard
- Visualize story flow and bottlenecks
- Track velocity and completion trends

## Common Questions

**Q: How often should I regenerate this?**
A: At minimum, weekly. Ideally before sprint planning and major stakeholder meetings.

**Q: Should I include all backlog stories?**
A: Include prioritized backlog stories. Exclude far-future or unrefined stories unless you want a complete inventory.

**Q: What if I have 100+ active stories?**
A: Use abbreviated format for backlog stories (just title and points). Consider filtering by epic or feature area.

**Q: How is this different from JIRA?**
A: It's a snapshot for specific point in time, optimized for reading/sharing, not real-time editing.

**Q: Should I commit this to git?**
A: Yes! Track changes over time and ensure team always has access to current snapshot.

## File Naming Convention

Recommended naming:
```
active-stories.md                    # Current snapshot
active-stories-2025-12-29.md        # Date-stamped archive
component-name-active-stories.md    # Component-specific
sprint-23-active-stories.md         # Sprint-specific
```

## Example Workflow

```
Monday (Sprint Planning):
├─ Export active stories from JIRA
├─ Generate active-stories.md
├─ Review stories in planning meeting
├─ Update sprint commitment
└─ Commit to repository

Daily (During Sprint):
├─ Reference during standup
├─ Update notes in JIRA (source of truth)
└─ No need to regenerate daily

Friday (End of Week):
├─ Regenerate active-stories.md
├─ Archive as active-stories-YYYY-MM-DD.md
├─ Share summary with stakeholders
└─ Identify blocked or stale stories

Next Monday (Repeat):
└─ Start new week with fresh snapshot
```

## Success Metrics

Track these to measure usefulness:
- **Team Usage**: How often team references the document
- **Staleness**: Average age of document (target <7 days)
- **Completeness**: % of stories with acceptance criteria
- **Accuracy**: % match with JIRA (should be 100% when fresh)

---

## Related Resources

- **milestones.csv**: Strategic objectives
- **MILESTONES_TEMPLATE_README.md**: How to track milestones
- **gap-analysis.md**: Milestone coverage analysis
- **GAP_ANALYSIS_README.md**: How to perform gap analysis
- **active-stories-template.md**: This template

## Questions & Feedback

Feel free to customize this template to fit your team's workflow. The goal is to make active work visible and accessible, not to create documentation overhead.

**Pro tip**: Start simple. You can always add more detail later as you identify what information is most valuable to your team.
