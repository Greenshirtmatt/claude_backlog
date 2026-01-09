# Gap Analysis README

## Overview

The Gap Analysis is a critical product management tool that identifies discrepancies between your strategic milestones (what you plan to build) and your active JIRA stories (what's actually being worked on). This analysis ensures nothing falls through the cracks and helps maintain alignment between strategy and execution.

## Purpose

**Why perform gap analysis?**
- Identify milestone objectives that lack corresponding implementation stories
- Catch planning oversights before they become delivery problems
- Ensure your team is working on what actually matters
- Maintain traceability from strategy to execution
- Surface work that needs to be broken down into actionable stories

## Structure

The gap analysis document follows a consistent structure:

### 1. Executive Summary
- Analysis metadata (date, files analyzed)
- High-level overview of findings
- Total gaps identified

### 2. Detailed Gap Analysis by Milestone
For each milestone:
- **Status indicator**: ✅ Complete, ⚠️ Partial Coverage, ❌ Missing Coverage
- **Covered Objectives**: List of objectives with corresponding stories
- **Missing Stories**: Objectives without JIRA story coverage
- **Recommendations**: Specific actions to close the gaps

### 3. Summary of Gaps by Priority
Gaps categorized by urgency and impact:
- **High Priority**: Work marked "In Progress" but no stories exist
- **Medium Priority**: Planned feature work
- **Lower Priority**: Infrastructure, documentation, optimization
- **Future Scope**: Next quarter or longer-term work
- **Cross-Team Coordination**: Dependencies on other teams

### 4. Recommendations
Actionable next steps divided into:
- Immediate Actions (do now)
- Planning Actions (for next sprint/quarter)
- Process Improvements (systemic changes)

### 5. Coverage Metrics
Quantitative view of milestone coverage:
- Total objectives vs. covered vs. missing
- Percentage breakdown
- Per-milestone coverage statistics

## How to Perform Gap Analysis

### Step 1: Gather Your Data
```bash
# You'll need:
1. Your milestones.csv file (strategic objectives)
2. Export of active JIRA stories (current sprint/backlog)
3. Access to completed stories (to verify "Completed" objectives)
```

### Step 2: Map Objectives to Stories
For each objective in your milestones:
1. Search JIRA for stories that implement this objective
2. Check story titles, descriptions, and acceptance criteria
3. Note partial matches (story covers some but not all of objective)
4. Mark as ✅ covered, ⚠️ partial, or ❌ missing

### Step 3: Document Gaps
For each gap:
- Note the objective and its milestone status
- Explain why existing stories don't cover it
- Provide a specific recommendation (e.g., "Create story for X")

### Step 4: Prioritize
Not all gaps are equal:
- **Critical**: "In Progress" milestones with no stories (team is blocked)
- **High**: "Planned" work for current quarter with no stories (planning gap)
- **Medium**: Next quarter work (planning ahead)
- **Low**: Future scope or nice-to-have features

### Step 5: Take Action
Use the gap analysis to:
- Create missing JIRA stories immediately
- Adjust milestone status if work isn't actually happening
- Re-prioritize work to align with actual capacity
- Communicate gaps to stakeholders

## Automation Opportunities

Consider automating parts of this process:

### Semi-Automated Approach
1. Export milestones to CSV
2. Query JIRA API for active stories
3. Use keyword matching to suggest potential coverage
4. Manually review and confirm matches
5. Generate gap report

### Manual Approach (Recommended for Small Teams)
1. Print milestones.csv
2. Open JIRA board
3. Go through each objective one by one
4. Document findings in gap-analysis.md

## Best Practices

### Do This
- ✅ Run gap analysis at least quarterly
- ✅ Update immediately before sprint planning
- ✅ Include stakeholders in gap review
- ✅ Create missing stories promptly
- ✅ Track gap closure rate as a metric
- ✅ Use gaps to inform backlog grooming

### Avoid This
- ❌ Creating stories just to close gaps (they should be real work)
- ❌ Treating 100% coverage as the only acceptable outcome
- ❌ Ignoring gaps marked "Future Scope" forever
- ❌ Running gap analysis and not acting on findings
- ❌ Making the analysis too detailed (focus on actionable gaps)

## Status Indicators Explained

| Indicator | Meaning | Action Required |
|-----------|---------|-----------------|
| ✅ COMPLETE | All objectives have story coverage | Monitor; verify stories are progressing |
| ⚠️ PARTIAL COVERAGE | Some objectives covered, some missing | Create stories for missing objectives |
| ❌ MISSING COVERAGE | No or minimal story coverage | Urgent: create stories or update milestone status |

## Integration with Other Processes

### Sprint Planning
Use gap analysis to:
- Identify work that should be in next sprint
- Verify sprint aligns with milestone priorities
- Surface dependencies before sprint starts

### Quarterly Planning
Use gap analysis to:
- Build next quarter's roadmap
- Identify when to staff up specific areas
- Communicate progress against strategic goals

### Stakeholder Updates
Use gap analysis to:
- Show alignment (or misalignment) between plan and execution
- Explain why certain features aren't progressing
- Justify requests for additional resources

## Template Usage

The provided `gap-analysis-template.md` includes:
- Fictional product features (Authentication, Data Pipeline, Analytics, etc.)
- Example coverage scenarios (complete, partial, missing)
- Sample recommendations
- Metrics section template

**To use the template:**
1. Copy `gap-analysis-template.md` to `gap-analysis.md`
2. Replace example milestones with your actual milestones from `milestones.csv`
3. Add your JIRA stories in the "Covered Objectives" sections
4. Identify and document gaps
5. Update metrics at the bottom
6. Share with your team for action

## Real-World Tips

### For Small Teams (1-5 people)
- Run gap analysis every 2 weeks
- Keep it lightweight—focus on high-priority gaps only
- Combine with sprint retrospective

### For Medium Teams (5-20 people)
- Run gap analysis monthly or every 2 sprints
- Assign gap analysis owner (rotating responsibility)
- Present findings in sprint planning or team sync

### For Large Teams (20+ people)
- Run gap analysis quarterly
- Create working group to review findings
- Present to leadership for resource allocation decisions
- Track gap closure rate as a team health metric

## Example Workflow

```
Week 1: Sprint Planning
├─ Review last gap analysis
├─ Verify gaps were addressed
└─ Plan sprint based on priorities

Week 4: Mid-Sprint
├─ Monitor story progress
└─ Note new work emerging

Week 6: Sprint End
├─ Run new gap analysis
├─ Compare with milestones
├─ Identify new gaps
└─ Prioritize for next sprint

Week 7: Stakeholder Update
├─ Share gap analysis findings
├─ Explain coverage metrics
└─ Request resources if needed
```

## Common Pitfalls and Solutions

### Pitfall 1: "We have too many gaps!"
**Solution:** Focus on high-priority gaps only. Not everything needs a story right now.

### Pitfall 2: "Stories don't map cleanly to objectives"
**Solution:** That's okay. One objective might need 3 stories, or 1 story might cover 2 objectives. Document the mapping.

### Pitfall 3: "Gap analysis takes too long"
**Solution:** Start with just one milestone. Build the muscle, then expand.

### Pitfall 4: "Teams ignore the findings"
**Solution:** Make it actionable. Don't just identify gaps—create the stories immediately.

### Pitfall 5: "Analysis is outdated immediately"
**Solution:** That's expected. Gap analysis is a snapshot. Re-run regularly.

## Success Metrics

Track these over time to measure effectiveness:
- **Gap Closure Rate**: % of identified gaps that get stories within 1 sprint
- **Coverage Trend**: % coverage this quarter vs. last quarter
- **Accuracy**: % of "covered" objectives that actually shipped as planned
- **Discovery Rate**: # of gaps found per analysis (should decrease over time)

---

## Additional Resources

- **milestones.csv**: Your strategic objectives
- **milestones_template.csv**: Template for creating milestones
- **MILESTONES_TEMPLATE_README.md**: Guide for using the milestone structure
- **gap-analysis-template.md**: This template file for gap analysis

## Questions & Customization

Feel free to customize this template:
- Add/remove priority categories
- Change coverage indicators (use different emojis or labels)
- Adjust metrics to match your team's needs
- Integrate with your specific JIRA workflow

The goal is to make gap analysis a useful, actionable part of your planning process—not bureaucratic overhead.
