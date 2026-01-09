# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Purpose

This is a JIRA work management repository for tracking product development milestones, managing backlog items, analyzing gaps between planned features and implementation, and creating well-structured JIRA stories. The repository uses templates and structured documents to maintain alignment between high-level product goals and granular implementation work.

## Repository Structure

### Templates Directory (`/templates/`)

Contains reusable templates for product management artifacts:

- **`milestones_template.csv`**: Hierarchical CSV template for tracking milestones and their constituent objectives
  - Format: `Milestone,Objective,Status,` (trailing comma intentional)
  - Milestones appear in column 1, objectives in column 2 with empty column 1
  - Empty rows (just commas) separate milestone groups

- **`jira-story-template.json`**: Default configuration for creating JIRA stories
  - Contains project key, issue type, components, assignee, labels, epic link
  - Must be used as the base for all JIRA story creation

- **`instructions_template.md`**: Comprehensive guide for repository workflow
  - Documents PRD referencing conventions (always cite line numbers)
  - Defines JIRA story creation process and formatting rules
  - Outlines gap analysis and reporting procedures

- **`MILESTONES_TEMPLATE_README.md`**: Documentation for the milestones CSV structure

### Expected Project Documents

Projects using this repository typically maintain:

- **PRD (Product Requirements Document)**: Source of truth for feature requirements
- **Milestones.csv**: Actual milestone tracking derived from PRD
- **active-stories.md**: Filtered view of active JIRA work (excludes Resolved/Closed)
- **gap-analysis.md**: Identifies missing JIRA stories mapped to milestone objectives
- **prd-findings-priority-stories.md**: Detailed analysis for high-priority missing stories

## JIRA Story Creation Workflow

### Critical Rules

1. **Never create JIRA stories proactively** - only create when explicitly requested by the user
2. **Always use** `jira-story-template.json` defaults (project key, components, assignee)
3. **Always reference PRD line numbers** in story descriptions (e.g., "PRD lines 100-120")
4. **Use JIRA wiki markup** for story descriptions

### Story Description Format

```
h3. Description
As a [role], I need [capability], so that [benefit].

h3. Current State (if applicable)
* Current situation

h3. Background (if applicable)
* Context and reasoning

h3. Acceptance Criteria
# Numbered list of specific, measurable criteria

h3. Technical Notes (if applicable)
* Implementation considerations
* Dependencies
* Data schema/API contracts

h3. Benefits (if applicable)
* Value and impact

h3. References
* PRD line numbers
* Related documents
* Gap analysis references
```

### Story Title Conventions

- Action-oriented and specific
- Good: "Migrate proof types from hard-coded prompt to dynamic service-based retrieval"
- Bad: "Update feature" or "Fix agent"

## Gap Analysis Process

1. Review milestone objectives from Milestones.csv
2. Compare against existing stories in active-stories.md
3. Identify missing implementation stories
4. Prioritize gaps (High, Medium, Low)
5. Document in gap-analysis.md with milestone mapping
6. Create detailed findings for priority stories with PRD references

## Report Generation Standards

- **Format**: All reports in Markdown (.md)
- **Naming**: lowercase-with-hyphens (e.g., gap-analysis.md, prd-findings.md)
- **Structure**: Clear headers, tables where appropriate, executive summaries
- **Updates**: Update existing reports rather than creating duplicates

## Milestones CSV Guidelines

### Structure
- Top-level milestones define features or capability groupings
- Objectives are specific deliverables under each milestone
- Keep objectives atomic and concrete

### Status Values
- Planned, In Design, In Progress, Completed, Blocked, On Hold

### Best Practices
- Update regularly (weekly recommended)
- Link objectives to JIRA tickets
- Avoid deep nesting - create separate milestones instead
- Keep realistic scope (10 well-defined objectives better than 50 aspirational ones)

## Acceptance Criteria Standards

- Use numbered lists for clarity
- Make criteria specific and measurable
- Include both functional and non-functional requirements
- Reference success metrics from PRD when available

## PRD Reference Conventions

- Always cite specific line numbers: "PRD lines 100-120" or "See PRD line 157"
- Include actual quotes or summaries from referenced sections
- Maintain traceability from stories back to requirements

## Integration Points

This repository workflow integrates with:
- JIRA ticket tracking (stories link to milestone objectives)
- Sprint planning (map objectives to sprint work)
- Status reporting (generate summaries from milestone data)
- Product strategy (gap analysis informs roadmap priorities)
