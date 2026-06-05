---
description: "Explore a web application, validate a feature, and create a Jira ticket if a defect is found. Use this prompt to demonstrate the full MCP workflow: browser control + Jira reporting in one agent session."
---

# Explore and Report

Perform exploratory testing on a web application and report findings to Jira.

## Inputs

- **URL**: ${input:url:URL of the application to test (e.g. https://demo.playwright.dev/todomvc)}
- **Feature**: ${input:feature:Feature to explore (e.g. Create a task, Filter tasks)}
- **Project key**: ${input:projectKey:Jira project key (e.g. SCRUM)}

## Steps

1. Navigate to `${input:url}`
2. Take a screenshot of the initial state
3. Perform the following actions to test `${input:feature}`:
   - Identify the main UI elements involved
   - Execute the happy path
   - Try at least one edge case (empty input, boundary value, unexpected action)
4. After each action, take a screenshot and describe what you observe
5. Compare observed behavior with expected behavior

## Decision

**If everything works as expected:**
- Summarize the test as PASS with screenshots as evidence

**If a defect is found:**
- Create a Jira issue in project `${input:projectKey}` with:
  - Summary: `[BUG] {short description}`
  - Description:
  **Steps to reproduce:**
1. ...
2. ...

**Expected:** ...
**Actual:** ...
**Evidence:** [screenshot attached]

- Priority: Medium

## Output

- Test result: PASS or FAIL
- Screenshots taken during the session
- Jira ticket URL if a defect was created