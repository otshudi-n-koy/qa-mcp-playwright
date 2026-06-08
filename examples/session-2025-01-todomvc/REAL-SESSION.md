# Real Session — How to capture live evidence

This file is a placeholder for a real session output.  
The `report.md` in this folder is a **representative example** of what a live agent session produces.

---

## To capture a real session

### Prerequisites
- VS Code with GitHub Copilot (Agent mode enabled)
- MCP servers configured in `.vscode/mcp.json`
- `jira-mcp` installed globally (`npm install -g jira-mcp`)
- Valid Jira Cloud credentials

### Steps

```bash
# 1. Clone the repo
git clone https://github.com/otshudi-n-koy/qa-mcp-playwright.git
cd qa-mcp-playwright

# 2. Create .vscode/mcp.json with your credentials (see README)

# 3. Open VS Code
code .

# 4. Start MCP servers (click "Démarrer" in .vscode/mcp.json)

# 5. Open Copilot Chat → switch to Agent mode

# 6. Load the prompt:
#    .github/prompts/explore-and-report.prompt.md

# 7. Fill in:
#    URL: https://demo.playwright.dev/todomvc
#    Feature: Create a task
#    Project key: SCRUM
```

### Expected outputs
- Agent trace in Copilot Chat (tool calls + observations)
- Screenshots saved by `browser_screenshot` tool calls
- Jira ticket created if a defect is found
- PASS/FAIL verdict with evidence summary

### Save your session
Once done:
1. Copy the full agent trace from Copilot Chat → paste into `report.md`
2. Screenshots → save as `screenshot-01-*.png`, `screenshot-02-*.png`, etc.
3. If a Jira ticket was created → add its URL and key to the report