# PRD Findings Template README

## Overview

The PRD Findings document bridges the gap between your Product Requirements Document (PRD) and your execution plan (JIRA stories). It analyzes your PRD to identify features and requirements that need corresponding implementation stories, provides detailed story recommendations with acceptance criteria, and assesses implementation readiness.

## Purpose

**Why create a PRD Findings document?**
- **PRD-to-Execution Bridge**: Systematically convert PRD requirements into actionable stories
- **Coverage Analysis**: Ensure all PRD requirements have corresponding implementation plans
- **Prioritization**: Identify which requirements are ready to implement vs need more definition
- **Acceptance Criteria**: Generate story-ready acceptance criteria directly from PRD content
- **Implementation Readiness**: Assess how well-defined each requirement is for engineering
- **Reference Traceability**: Link every story back to specific PRD sections and line numbers

## Structure

### Header Information
- **Analysis Date**: When the PRD analysis was performed
- **Source Document**: Which PRD was analyzed

### Story Sections (Repeating Pattern)

For each identified story:

1. **Story Title and Priority**
   - Clear, actionable title
   - Milestone status (In Progress, Planned, etc.)
   - Priority level (HIGH, MEDIUM, LOW)

2. **PRD Coverage Assessment**
   - ✅ Well Documented: Ready to implement
   - ⚠️ Partially Documented: Needs clarification
   - ❌ Missing Documentation: Needs PRD updates

3. **Key PRD Sections**
   - Direct quotes from PRD with line number references
   - Multiple sections that define the requirement
   - Success metrics from PRD

4. **Recommended Story Details**
   - Story title
   - User story format description
   - Detailed acceptance criteria (10+ items typical)
   - Technical notes and considerations
   - Dependencies

### Summary Tables

- **PRD Coverage Table**: Quick view of all stories and readiness
- **Key Takeaways**: Synthesis of findings
- **Recommendations**: Actionable next steps

## How to Create PRD Findings Document

### Step 1: Read the PRD Thoroughly

- Identify all features and requirements
- Note which have success metrics defined
- Mark sections that are well-defined vs vague
- List non-functional requirements (NFRs)

### Step 2: Cross-Reference with Milestones

- Review your milestones.csv
- Identify milestone objectives that appear in PRD
- Look for PRD features not in milestones (new work)
- Look for milestone objectives not in PRD (needs documentation)

### Step 3: Cross-Reference with Active Stories

- Check which PRD requirements already have stories
- Identify PRD sections without story coverage
- Note partial coverage (story exists but incomplete)

### Step 4: Analyze Each Missing Story

For each PRD section without a story:

1. **Extract requirements** from PRD text
2. **Identify success metrics** mentioned in PRD
3. **Assess completeness** - Is this ready to implement?
4. **Draft acceptance criteria** based on PRD details
5. **Note dependencies** on other features or infrastructure

### Step 5: Prioritize Stories

Consider:
- **Milestone status** - "In Progress" = HIGH priority
- **Dependency chains** - Foundational work = higher priority
- **PRD clarity** - Well-documented = easier to start
- **Business impact** - Revenue/compliance = higher priority

### Step 6: Assess Implementation Readiness

For each story, rate readiness:
- **High**: Can start immediately, all details clear
- **Medium**: Can start after design/architecture session
- **Medium-Low**: Needs PRD clarification first
- **Low**: Needs spike/research before story creation

## PRD Coverage Indicators

### ✅ Well Documented

**Criteria:**
- Feature clearly defined with specific requirements
- Success metrics provided with targets
- User journey or workflow described
- Technical constraints or requirements noted
- Acceptance criteria can be written directly from PRD

**Example:**
> "Authentication service must support username/password (Section 3.2), MFA via SMS or authenticator app (Section 3.2.1), with 99.5% success rate (Section 7.3) and <500ms latency (Section 7.3)"

**Action:** Create story immediately

---

### ⚠️ Partially Documented

**Criteria:**
- Feature mentioned but details incomplete
- Success metrics missing or vague
- Some technical details but gaps exist
- Acceptance criteria requires inference

**Example:**
> "System should provide notifications (Section 4.5)" - but doesn't specify notification types, delivery methods, or success criteria

**Action:** Clarify with PM, then create story

---

### ❌ Missing Documentation

**Criteria:**
- Feature not mentioned in PRD at all
- Only implied by other requirements
- No success metrics
- Technical approach completely undefined

**Example:**
> Milestone says "Implement caching layer" but PRD has no mention of caching strategy, requirements, or metrics

**Action:** Update PRD first, then create story

## Best Practices

### Do This
- ✅ **Include line numbers** - Reference specific PRD sections (e.g., "Line 887")
- ✅ **Direct quotes** - Use exact PRD language to avoid misinterpretation
- ✅ **Comprehensive AC** - Write 8-12 acceptance criteria per story
- ✅ **Extract metrics** - Pull success metrics directly from PRD
- ✅ **Note dependencies** - Identify prerequisite work
- ✅ **Assess readiness** - Be honest about what's ready vs needs clarification
- ✅ **Prioritize ruthlessly** - Focus on HIGH priority items first

### Avoid This
- ❌ **Inventing requirements** - Don't add details not in PRD
- ❌ **Vague AC** - "System works correctly" is not an acceptance criterion
- ❌ **Ignoring gaps** - If PRD is unclear, mark as "needs clarification"
- ❌ **Creating all stories** - This is a recommendation document, not a backlog
- ❌ **One-size-fits-all** - Some PRD sections need multiple stories

## Detail Level for Story Recommendations

### HIGH Priority Stories (Comprehensive Detail)

Include:
- Full user story description
- 10-15 detailed acceptance criteria
- Technical implementation notes
- Specific libraries or technologies to use
- Integration points and dependencies
- Success metrics and targets
- Testing requirements
- Security/compliance considerations

**Why:** These will be implemented soon, so engineers need complete details.

---

### MEDIUM Priority Stories (Moderate Detail)

Include:
- User story description
- 6-10 acceptance criteria
- High-level technical approach
- Key dependencies
- Success metrics
- Open questions to resolve

**Why:** These might be implemented next quarter, so provide enough detail for planning.

---

### LOW Priority Stories (Light Detail)

Include:
- User story description
- 3-5 key acceptance criteria
- High-level scope
- Dependencies (if known)

**Why:** These are future scope, details can be fleshed out when prioritized.

## Use Cases

### Sprint Planning
- Review HIGH priority stories for upcoming sprint
- Verify all details are in PRD before committing
- Identify stories that need clarification before starting

### Backlog Grooming
- Work through MEDIUM priority stories
- Refine acceptance criteria
- Break large stories into smaller ones
- Update PRD if gaps found

### Quarterly Planning
- Review all recommended stories
- Map to product roadmap
- Identify resourcing needs
- Sequence work based on dependencies

### PRD Review
- Validate PRD completeness
- Identify sections that need more detail
- Ensure success metrics defined for all features
- Verify NFRs are covered

### Gap Analysis Companion
- Use alongside gap-analysis.md
- PRD Findings: "What's in PRD but not in stories"
- Gap Analysis: "What's in milestones but not in stories"
- Together: Complete coverage picture

## Common Patterns

### Pattern 1: Single PRD Section → Single Story

**Example:**
- PRD Section 3.4: "User Profile Management"
- Story: "Implement user profile management"

**When to use:** Feature is well-scoped and can be completed in one story (1-2 sprints)

---

### Pattern 2: Single PRD Section → Multiple Stories

**Example:**
- PRD Section 5: "Production Readiness"
- Story 5A: "CI/CD Pipeline"
- Story 5B: "Performance Testing"
- Story 5C: "Security Hardening"
- Story 5D: "Operational Runbooks"

**When to use:** Large PRD section covers multiple distinct work streams

---

### Pattern 3: Multiple PRD Sections → Single Story

**Example:**
- PRD Section 3.2 (Auth requirements) + Section 5.1 (Security) + Section 7.3 (Metrics)
- Story: "Implement secure authentication service"

**When to use:** Story requires synthesizing requirements from multiple PRD sections

---

### Pattern 4: PRD Requirement + NFR → Enhanced Story

**Example:**
- PRD Section 4.2 (Feature) + NFR-005 (Logging requirement)
- Story includes: Feature implementation + comprehensive logging

**When to use:** Non-functional requirements affect multiple features

## Integration with Other Documents

### Milestones → PRD Findings → Gap Analysis Flow

```
1. milestones.csv
   ↓ (What we plan to build)
2. PRD - Detailed requirements
   ↓ (Analyze PRD)
3. PRD Findings - Recommended stories
   ↓ (What should exist in JIRA)
4. active-stories.md - Current JIRA stories
   ↓ (Compare)
5. gap-analysis.md - Identify gaps
   ↓ (Fill gaps)
6. Create missing stories in JIRA
```

### Recommended Workflow

**Week 1: PRD Review**
- Read PRD thoroughly
- Create PRD Findings document
- Identify top 5-10 priority stories

**Week 2: Story Creation**
- Create HIGH priority stories in JIRA
- Use acceptance criteria from PRD Findings
- Clarify any PRD gaps with PM

**Week 3: Gap Analysis**
- Run gap analysis comparing milestones vs stories
- Validate PRD Findings stories are captured
- Identify any remaining gaps

**Week 4: Backlog Grooming**
- Refine created stories
- Estimate story points
- Sequence based on dependencies

## Customization Tips

Adapt this template based on:

1. **PRD Format**: If your PRD uses different sections, adjust references
2. **Team Size**: Smaller teams can use lighter-weight format
3. **Domain**: Add domain-specific technical considerations
4. **Compliance**: Add compliance-specific acceptance criteria
5. **Your Workflow**: Integrate with existing planning processes

## Automation Opportunities

### Semi-Automated Approach

1. **PRD Parsing**: Use script to extract sections and requirements
2. **Keyword Matching**: Identify sections mentioning features in milestones
3. **Metrics Extraction**: Parse sections with percentages, targets, timeframes
4. **Story Template**: Auto-generate story skeleton from PRD sections
5. **Manual Refinement**: Engineer adds details and acceptance criteria

### AI-Assisted Approach

Use LLM to:
- Analyze PRD and identify distinct features
- Extract success metrics and targets
- Generate initial acceptance criteria
- Assess implementation readiness
- Identify dependencies between features

**Important:** Always manually review AI-generated content for accuracy.

## Success Metrics

Track these to measure effectiveness:

- **Coverage**: % of PRD requirements with recommended stories
- **Accuracy**: % of created stories that match PRD Findings recommendations
- **Readiness**: % of HIGH priority stories successfully implemented without major changes
- **Gap Closure**: % of PRD Findings stories that get created in JIRA within 2 weeks
- **PRD Quality**: # of PRD clarifications needed before story creation

## Common Pitfalls

### Pitfall 1: "PRD is too vague to create stories"

**Solution:** Document this in PRD Findings with "⚠️ Partially Documented" or "❌ Missing Documentation". Request PRD update before creating story.

---

### Pitfall 2: "Too many stories recommended (50+)"

**Solution:** Focus on top 10 HIGH priority items first. Add others to appendix or separate document.

---

### Pitfall 3: "Acceptance criteria are too generic"

**Solution:** Use specific metrics and targets from PRD. "System is fast" → "API p95 latency <500ms (Section 6.1)"

---

### Pitfall 4: "Stories created but PRD updated later"

**Solution:** Version your PRD Findings with date. When PRD updates, regenerate findings for affected sections.

---

### Pitfall 5: "Engineering disagrees with story breakdown"

**Solution:** PRD Findings are recommendations, not mandates. Collaborate with engineers to refine scope and breakdown.

## Template Structure Explained

The template follows this format for each story:

```markdown
## Story X: [Clear, Actionable Title]

**Milestone Status:** [In Progress/Planned/etc.]
**Priority:** [HIGH/MEDIUM/LOW] ([Reasoning])

### PRD Coverage: [✅/⚠️/❌] [Assessment]

**Key PRD Sections:**

**Section Name (Lines XXX-YYY):**
- [Direct quote or summary]
- [Key requirement]
- [Success metric]

[Repeat for all relevant sections]

### Recommended Story Details:

**Story Title:** [Title for JIRA]

**Description:**
As a [role], I need [capability], so that [benefit].

**Acceptance Criteria:**
1. [Specific, testable criterion]
2. [Another criterion]
...

**Technical Notes:**
- [Implementation approach]
- [Libraries/frameworks to use]
- [Integration points]
```

This structure ensures:
- Clear traceability to PRD
- Ready-to-use acceptance criteria
- Implementation guidance
- Priority and readiness assessment

---

## Related Resources

- **PRD**: Your product requirements document
- **milestones.csv**: Strategic objectives
- **active-stories.md**: Current JIRA stories
- **gap-analysis.md**: Milestone coverage analysis
- **prd-findings-template.md**: This template

## Questions & Feedback

This template is designed to be customized. The goal is to ensure every PRD requirement becomes a well-defined, implementable story—not to create extra documentation work.

**Pro tip**: Start with your top 5 priority gaps. Get those right before attempting to analyze the entire PRD.
