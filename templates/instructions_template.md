# JIRA Work Repository Instructions

## Project Context

**Project:** [AI Agent Project Name]
**Team:** [Team Name]
**Product Manager:** [PM Name]
**Purpose:** This repository is used to review JIRA stories, analyze milestones, identify gaps, and manage updates to JIRA stories for the project component.

---

## Repository Files

### Core Documents

**PRD - [Product Requirements Document].md**
- Product Requirements Document defining the AI agent functionality
- Contains detailed specifications for key features and workflows
- Reference PRD line numbers when creating stories or documenting requirements
- Primary source of truth for feature requirements

**Milestones.csv**
- High-level EPIC milestones derived from the PRD
- Contains milestone objectives, status, and descriptions
- Used to track progress and identify missing implementation stories
- Maps to broader product goals and deliverables

**active-stories.md**
- Filtered view of JIRA stories showing only active work (In Progress, To Do, Backlog)
- Excludes Resolved and Closed stories
- Contains active stories with full descriptions where available
- Generated from the full stories list file
- Useful for sprint planning and active backlog management

**gap-analysis.md**
- Analysis document identifying missing JIRA stories based on milestone objectives
- Maps milestones to existing stories and highlights gaps
- Prioritizes missing stories (High, Medium, Low priority)
- Provides recommendations for story creation
- Should be updated whenever new milestones are added or stories are created

**prd-findings-priority-stories.md**
- Detailed analysis of priority missing stories
- Includes PRD references, line numbers, and specific requirements
- Provides recommended story details and acceptance criteria
- Used to create well-defined JIRA stories with proper context

---

## JIRA Story Management

### Creating JIRA Stories

**IMPORTANT:** Only create JIRA stories after being explicitly prompted by the user.

**Template:** Always use `.jira-story-template.json` for creating new JIRA stories.

**Default Values from Template:**
- **Project Key:** [YOUR_PROJECT_KEY]
- **Issue Type:** User Story
- **Component:** [YOUR_COMPONENT]
- **Assignee:** [default_assignee]
- **Labels:** (empty by default, add as needed)
- **Epic Link:** (empty by default, link as needed)

**Story Description Format:**
Use JIRA wiki markup with the following sections:
```
h3. Description
As a [role], I need [capability], so that [benefit].

h3. Current State (if applicable)
* Current situation

h3. Background (if applicable)
* Context and reasoning

h3. Acceptance Criteria
# Numbered list of criteria

h3. Technical Notes (if applicable)
* Implementation considerations

h3. Benefits (if applicable)
* Value and impact

h3. References
* PRD line numbers
* Related documents
* Gap analysis references
```

**Best Practices:**
- Always reference PRD line numbers when applicable (e.g., "PRD lines 100-120")
- Link stories to milestone objectives from gap analysis
- Include specific, measurable acceptance criteria
- Add technical context from PRD when available
- Note related stories or dependencies

---

## Workflow Guidelines

### Gap Analysis Process
1. Review milestone objectives from Milestones.csv
2. Compare against existing stories in active-stories.md
3. Identify missing stories and document in gap-analysis.md
4. Prioritize gaps (High, Medium, Low)
5. Create detailed findings for priority stories

### Story Creation Process
1. Wait for explicit user request to create JIRA story
2. Review PRD for detailed requirements
3. Use `.jira-story-template.json` defaults
4. Include all relevant sections (Description, AC, Technical Notes, References)
5. Create story in JIRA using appropriate tool
6. Confirm successful creation with ticket number and URL

### Report Generation
- **Format:** All reports must be created in Markdown (.md) format
- **Naming:** Use descriptive, lowercase-with-hyphens naming (e.g., gap-analysis.md, prd-findings.md)
- **Structure:** Include clear headers, tables where appropriate, and summaries
- **Updates:** Keep existing reports up-to-date rather than creating duplicate files

---

## Conventions

### PRD References
- Always cite specific line numbers when referencing PRD content
- Format: "PRD lines 100-120" or "See PRD line 157"
- Include actual quotes or summaries from referenced sections

### Story Titles
- Be specific and action-oriented
- Example: "Migrate proof types from hard-coded prompt to dynamic service-based retrieval"
- Avoid vague titles like "Update feature" or "Fix agent"

### Acceptance Criteria
- Use numbered lists for clarity
- Make criteria specific and measurable
- Include both functional and non-functional requirements
- Reference success metrics from PRD when available

### Technical Notes
- Include implementation considerations
- Note dependencies on other systems or services
- Mention data schema, API contracts, or integration points
- Flag decisions that need architecture review

---

## Component-Specific Context

### [Your AI Agent Component]
- Focus: [Core functionality description]
- Key Features: [Feature 1], [Feature 2], [Feature 3], [Feature 4]
- Policy: [Reference documentation]
- Success Metrics: [Define your success criteria]

### Key Feature Types
- [Number] valid feature types for [core functionality]
- Implementation approach considerations
- See PRD for complete list and definitions

### Key Milestones
1. [Milestone 1] (Status)
2. [Milestone 2] (Status)
3. [Milestone 3] (Status)
4. [Milestone 4] (Status)
5. [Milestone 5] (Status)
6. [Milestone 6] (Status)

---

## Notes

- This repository is maintained by [PM Name]
- Changes to milestones, PRD, or gap analysis should trigger review of active stories
- Keep gap-analysis.md current as new stories are created
- Regular reviews ensure alignment between milestones and implementation
