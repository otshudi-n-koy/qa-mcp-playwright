# Examples

This folder contains session outputs from the QA MCP agent.

Each session is a self-contained folder with:
- `report.md` — PASS/FAIL verdict, agent trace, assertions
- `screenshot-*.png` — visual evidence captured by MCP Playwright
- `REAL-SESSION.md` — instructions to reproduce the session locally

---

## Sessions

| Session | Target | Feature | Verdict |
|---------|--------|---------|---------|
| [session-2025-01-todomvc](./session-2025-01-todomvc/report.md) | TodoMVC | Create a task | ✅ PASS |

---

## Adding a new session

1. Create a folder: `session-YYYY-MM-<target>/`
2. Run the agent with `.github/prompts/explore-and-report.prompt.md`
3. Save the trace as `report.md` (use existing session as template)
4. Copy screenshots into the folder
5. Add a row to the table above

---

> Sessions marked with 🔴 FAIL include an auto-created Jira ticket link in the report.