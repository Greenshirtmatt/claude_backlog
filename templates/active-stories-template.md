# Product Component - Active Jira Stories

**Total Active Issues:** XX
**Generated:** YYYY-MM-DD
**Component:** [COMPONENT_NAME]
**Note:** This file includes only In Progress, To Do, and Backlog stories. Resolved and Closed stories are excluded.

---
## Active Stories (Sorted by Status)

## In Progress

### PROJ-101
**Implement Multi-Factor Authentication**
- **Status:** In Progress
- **Assignee:** Smith, John
- **Created:** 12/1/2025, 10:00:00 AM
- **Updated:** 12/15/2025, 3:30:00 PM
- **Story Points:** 5

**Description:**
As a user, I want to enable multi-factor authentication on my account so that I can enhance my account security beyond just a password.

**Notes:**
- Support for both SMS and authenticator app
- Integration with existing auth service
- Need to handle recovery codes
- Mobile app support required

**Design:**
- Figma link: [Insert design link]
- User flow diagram: [Insert flow link]

**Acceptance Criteria:**

*Happy Path*
1. User navigates to security settings
2. User selects "Enable MFA" option
3. User chooses MFA method (SMS or authenticator app)
4. User completes verification process
5. User receives recovery codes
6. MFA is successfully enabled

*Alternative Paths*
1. User can disable MFA after re-authentication
2. User can switch between MFA methods
3. Recovery code flow works when user loses device

**To Do:**
- Complete SMS provider integration
- Finalize recovery code generation logic
- Write integration tests


### PROJ-102
**Database Query Optimization for Reports**
- **Status:** In Progress
- **Assignee:** Johnson, Sarah
- **Created:** 11/20/2025, 9:15:00 AM
- **Updated:** 12/16/2025, 2:45:00 PM
- **Story Points:** 3

**Description:**
As a system administrator, I want the reporting dashboard to load faster so that I can make timely business decisions.

**Needs Definition:**
- Identify top 5 slowest queries
- Determine acceptable performance targets
- Work with DBA on index strategy

**Notes:**
- Current dashboard load time: 15-20 seconds
- Target load time: <3 seconds
- Focus on user activity reports and transaction summaries

**Acceptance Criteria:**
1. Dashboard load time reduced to <3 seconds for 95th percentile
2. Database query execution time tracked and logged
3. Indexes added for commonly filtered columns
4. Query results cached appropriately
5. Performance metrics dashboard updated


### PROJ-103
**Add Export Functionality to Data Grid**
- **Status:** In Progress
- **Assignee:** Lee, Michael
- **Created:** 11/15/2025, 2:30:00 PM
- **Updated:** 12/17/2025, 11:20:00 AM
- **Story Points:** Not set

**Description:**
As a business analyst, I want to export grid data to CSV and Excel formats so that I can perform offline analysis and share data with stakeholders.

**Notes:**
- Support CSV and XLSX formats
- Handle large datasets (>10k rows) with pagination
- Respect user permissions (only export visible data)
- Include column headers and formatting

**Implementation Notes:**
- Use library X for CSV generation
- Use library Y for Excel generation
- Server-side processing for large exports
- Progress indicator for long-running exports

**Questions:**
- Should we limit export size? If so, what's the max?
- Do we need to log export actions for compliance?

**Acceptance Criteria:**
1. User can select "Export" from grid toolbar
2. User can choose between CSV and Excel formats
3. Export includes all visible columns and respects current filters
4. Large exports (>5k rows) show progress indicator
5. Exported files download with appropriate filename (e.g., "report_2025-12-17.xlsx")


## To Do

### PROJ-104
**Implement Password Reset Flow**
- **Status:** To Do
- **Assignee:** Davis, Emily
- **Created:** 12/10/2025, 8:00:00 AM
- **Updated:** 12/15/2025, 10:00:00 AM
- **Story Points:** 3


### PROJ-105
**Add Sorting to Customer List View**
- **Status:** To Do
- **Assignee:** Wilson, David
- **Created:** 12/8/2025, 1:30:00 PM
- **Updated:** 12/14/2025, 4:15:00 PM
- **Story Points:** 2


### PROJ-106
**Fix Broken Links in Help Documentation**
- **Status:** To Do
- **Assignee:** Martinez, Lisa
- **Created:** 12/5/2025, 11:00:00 AM
- **Updated:** 12/12/2025, 9:30:00 AM
- **Story Points:** 1


### PROJ-107
**Update Terms of Service Page**
- **Status:** To Do
- **Assignee:** Anderson, Chris
- **Created:** 12/1/2025, 3:00:00 PM
- **Updated:** 12/10/2025, 2:00:00 PM
- **Story Points:** Not set


### PROJ-108
**Implement Session Timeout Warning**
- **Status:** To Do
- **Assignee:** Taylor, Jessica
- **Created:** 11/28/2025, 10:30:00 AM
- **Updated:** 12/9/2025, 1:15:00 PM
- **Story Points:** 2


### PROJ-109
**Add Filter by Date Range to Transaction History**
- **Status:** To Do
- **Assignee:** Brown, Robert
- **Created:** 11/25/2025, 2:45:00 PM
- **Updated:** 12/8/2025, 11:00:00 AM
- **Story Points:** 3


### PROJ-110
**Create User Onboarding Tutorial**
- **Status:** To Do
- **Assignee:** White, Amanda
- **Created:** 11/22/2025, 9:00:00 AM
- **Updated:** 12/7/2025, 3:30:00 PM
- **Story Points:** 5


### PROJ-111
**Fix Mobile Responsiveness on Settings Page**
- **Status:** To Do
- **Assignee:** Garcia, Carlos
- **Created:** 11/20/2025, 4:00:00 PM
- **Updated:** 12/6/2025, 10:00:00 AM
- **Story Points:** Not set


### PROJ-112
**Add Bulk Actions to User Management**
- **Status:** To Do
- **Assignee:** Miller, Jennifer
- **Created:** 11/18/2025, 1:15:00 PM
- **Updated:** 12/5/2025, 2:45:00 PM
- **Story Points:** 5


### PROJ-113
**Implement Email Notification Preferences**
- **Status:** To Do
- **Assignee:** Moore, Kevin
- **Created:** 11/15/2025, 11:30:00 AM
- **Updated:** 12/4/2025, 9:00:00 AM
- **Story Points:** 3


## Backlog

### PROJ-201
**Add Dark Mode Theme**
- **Status:** Backlog
- **Assignee:** Rodriguez, Maria
- **Created:** 11/10/2025, 10:00:00 AM
- **Updated:** 11/30/2025, 2:00:00 PM
- **Story Points:** 8

**Description:**
As a user, I want a dark mode option so that I can reduce eye strain when using the application in low-light environments.

**Notes:**
- Implement theme toggle in user settings
- Store preference in user profile
- Apply theme across all pages and components
- Use CSS variables for color management
- Follow accessibility guidelines for contrast ratios

**Acceptance Criteria:**
1. User can toggle between light and dark themes
2. Theme preference persists across sessions
3. All UI components respect the selected theme
4. Contrast ratios meet WCAG AA standards
5. Images and logos have appropriate versions for each theme


### PROJ-202
**Implement Advanced Search with Filters**
- **Status:** Backlog
- **Assignee:** Jackson, Tom
- **Created:** 11/5/2025, 3:30:00 PM
- **Updated:** 11/28/2025, 11:00:00 AM
- **Story Points:** 8


### PROJ-203
**Add API Rate Limiting**
- **Status:** Backlog
- **Assignee:** Harris, Nicole
- **Created:** 11/1/2025, 9:00:00 AM
- **Updated:** 11/25/2025, 4:00:00 PM
- **Story Points:** 5


### PROJ-204
**Create Admin Dashboard for System Metrics**
- **Status:** Backlog
- **Assignee:** Clark, Brian
- **Created:** 10/28/2025, 2:00:00 PM
- **Updated:** 11/22/2025, 10:30:00 AM
- **Story Points:** 13


### PROJ-205
**Implement Audit Log for User Actions**
- **Status:** Backlog
- **Assignee:** Lewis, Rachel
- **Created:** 10/25/2025, 11:00:00 AM
- **Updated:** 11/20/2025, 3:00:00 PM
- **Story Points:** 8


### PROJ-206
**Add Webhooks for External Integrations**
- **Status:** Backlog
- **Assignee:** Walker, James
- **Created:** 10/22/2025, 1:30:00 PM
- **Updated:** 11/18/2025, 9:00:00 AM
- **Story Points:** 13


### PROJ-207
**Implement Data Retention Policy Automation**
- **Status:** Backlog
- **Assignee:** Hall, Michelle
- **Created:** 10/20/2025, 10:00:00 AM
- **Updated:** 11/15/2025, 2:00:00 PM
- **Story Points:** 8


### PROJ-208
**Add Support for Custom Fields in Forms**
- **Status:** Backlog
- **Assignee:** Young, Steven
- **Created:** 10/18/2025, 4:00:00 PM
- **Updated:** 11/12/2025, 11:00:00 AM
- **Story Points:** 13


### PROJ-209
**Create Mobile App Companion**
- **Status:** Backlog
- **Assignee:** Allen, Laura
- **Created:** 10/15/2025, 2:30:00 PM
- **Updated:** 11/10/2025, 1:00:00 PM
- **Story Points:** 21


### PROJ-210
**Implement Single Sign-On (SSO)**
- **Status:** Backlog
- **Assignee:** King, Patrick
- **Created:** 10/12/2025, 9:00:00 AM
- **Updated:** 11/8/2025, 10:00:00 AM
- **Story Points:** 13


---

## Summary Statistics

### By Status
- **In Progress:** 3 issues
- **To Do:** 10 issues
- **Backlog:** 10 issues
- **Total Active:** 23 issues

### By Assignee (Top Contributors)
- **Smith, John:** 2 issues
- **Johnson, Sarah:** 2 issues
- **Lee, Michael:** 1 issue
- **Davis, Emily:** 1 issue
- **Wilson, David:** 1 issue
- **Martinez, Lisa:** 1 issue
- **Others:** 15 issues

### Story Points
- **Total Points Set:** 85 points (across 18 issues)
- **No Points Set:** 5 issues
