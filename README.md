# qa-mcp-playwright

> QA Automation toolkit demonstrating MCP (Model Context Protocol) integration —
> browser control with Playwright and Jira reporting, orchestrated by an AI agent.

**Author:** N'Koy Otshudi — [nkoyotshudi.fr](https://nkoyotshudi.fr)  
**Stack:** MCP Playwright · MCP Jira · VS Code Copilot · GitHub Copilot Agent  
**Certification context:** ISTQB CT-GenAI (in progress)

---

## What this project demonstrates

The shift from "AI that suggests" to "AI that acts" — an agent that controls
a real browser, validates features, and creates Jira tickets autonomously.

| CT-GenAI Chapter | What's demonstrated here |
|---|---|
| Ch.1 — GenAI Foundations | Agent/tool-use pattern via MCP protocol |
| Ch.2 — Quality Attributes | Autonomous validation with screenshot evidence |
| Ch.4 — Evaluation Methods | PASS/FAIL decision with observable evidence |
| Ch.7 — AI in Test Process | Full loop: explore → observe → report → ticket |

---

## How it works

Copilot Agent (VS Code)
│
├── MCP Playwright ──► browser_navigate, browser_click,
│                       browser_fill, browser_screenshot
│
└── MCP Jira ────────► jira_create_issue, jira_get_issue

**In practice:**
1. You describe what to test in Copilot Chat
2. The agent navigates the app, interacts, takes screenshots
3. If a defect is found → Jira ticket created automatically
4. If all passes → PASS report with evidence

---

## Project structure

qa-mcp-playwright/
├── .github/
│   ├── agents/
│   │   └── qa-mcp-agent.md              # MCP-powered QA agent
│   ├── instructions/                     # (coming soon)
│   └── prompts/
│       └── explore-and-report.prompt.md # Explore + Jira report workflow
├── examples/                             # Session outputs and screenshots
├── .vscode/
│   └── mcp.json                         # MCP servers config (not committed)
└── .env.local                           # Credentials (not committed)

---

## Getting started

### Prerequisites
- VS Code with GitHub Copilot extension
- Node.js 18+
- A Jira Cloud account (free at atlassian.net)

### Setup

```bash
# 1. Clone the repo
git clone https://github.com/otshudi-n-koy/qa-mcp-playwright.git
cd qa-mcp-playwright

# 2. Create .vscode/mcp.json (not committed — contains credentials)
mkdir -p .vscode
```

Create `.vscode/mcp.json`:
```json
{
  "servers": {
    "playwright": {
      "command": "npx",
      "args": ["@playwright/mcp@latest"]
    },
    "jira": {
      "command": "jira-mcp",
      "env": {
        "JIRA_INSTANCE_URL": "https://your-instance.atlassian.net",
        "JIRA_USER_EMAIL": "your@email.com",
        "JIRA_API_KEY": "your-api-token"
      }
    }
  }
}
```

```bash
# 3. Install jira-mcp globally
npm install -g jira-mcp

# 4. Open VS Code and start MCP servers
# Click "Démarrer" on each server in .vscode/mcp.json
```

### Run the demo

In Copilot Chat (Agent mode):

Use the explore-and-report prompt with:

URL: https://demo.playwright.dev/todomvc
Feature: Create a task
Project key: SCRUM

---

## Related projects

- [qa-genai-toolkit](https://github.com/otshudi-n-koy/qa-genai-toolkit) — LLM-assisted test generation from User Stories
- [qa-genai-evaluator](https://github.com/otshudi-n-koy/qa-genai-evaluator) — LLM output evaluation framework *(coming soon)*

---

## References

- [MCP Playwright](https://github.com/microsoft/playwright-mcp)
- [Jira MCP](https://www.npmjs.com/package/jira-mcp)
- [ISTQB CT-GenAI Syllabus](https://istqb.org)