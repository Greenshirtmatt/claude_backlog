# Milestones Template

## Overview

This template provides a structure for tracking product development milestones and their constituent objectives. It's designed to help product managers maintain clear visibility into feature development status and dependencies.

## Structure

The CSV uses a hierarchical structure:

- **Milestone**: Top-level feature or capability grouping
- **Objective**: Specific deliverable or task that contributes to the milestone
- **Status**: Current state of work (e.g., Planned, In Design, In Progress, Completed)

### Format

```csv
Milestone,Objective,Status,
[Feature Name],[Specific deliverable],[Status],
,[Another objective for same milestone],[Status],
,[Yet another objective],[Status],
,,
[Next Feature Name],[First objective],[Status],
```

**Key patterns:**
- Each milestone starts with a name in the first column
- Subsequent rows with empty first column represent objectives under that milestone
- Empty rows (just commas) separate milestone groups
- Trailing comma is intentional for CSV parsing consistency

## How to Use

1. **Copy the template**: Use `milestones_template.csv` as your starting point
2. **Define your milestones**: Replace example feature names with your actual product features or capabilities
3. **Break down objectives**: List the specific deliverables needed to achieve each milestone
4. **Track status**: Update the status as work progresses
5. **Keep it updated**: This becomes your single source of truth for milestone tracking

## Status Values

Common status values (customize to your workflow):
- **Planned**: Defined but not yet started
- **In Design**: Requirements/design phase
- **In Progress**: Active development
- **Completed**: Done and deployed
- **Blocked**: Work cannot proceed due to dependencies
- **On Hold**: Deliberately paused

## Integration with This Repository

This CSV can be used in conjunction with:
- Jira ticket tracking (link tickets to objectives)
- Sprint planning (map objectives to sprints)
- Status reporting (generate summaries from milestone data)
- Gap analysis (identify missing capabilities)

## Tips for Success

1. **Keep objectives atomic**: Each objective should be a single, concrete deliverable
2. **Avoid nesting too deeply**: If you need sub-objectives, create a separate milestone
3. **Update regularly**: Stale data makes this useless—review weekly
4. **Link to tickets**: Reference Jira tickets or PRs in your tracking system
5. **Be realistic**: Better to show 10 well-scoped objectives than 50 aspirational ones

## Example Usage

The template includes generic examples across common product development areas:
- Authentication features
- Data processing pipelines
- Analytics capabilities
- Platform stability work
- Production readiness tasks

Replace these with your actual product features while maintaining the same structural pattern.
