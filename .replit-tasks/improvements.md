# Replit Agent Task Spec — build-your-own-openclaw

## Instructions for Replit Agent
Read this file carefully before touching any code.
Commit all changes with prefix "replit: " and push to main when done.

## Stack Rules
- Python 3.11+
- AI → claude-sonnet-4-6 via Anthropic API
- Commit and push every change

## Context
This is a step-by-step tutorial (18 steps) for building your own AI agent,
progressing from a simple chat loop to a lightweight OpenClaw.

Our fork vs czl9707/build-your-own-openclaw comparison:
- Our fork has GAP.md documenting intentional simplifications vs picklebot
- Missing from our fork vs czl9707: REST API endpoints (intentional), template substitution (intentional)
- Our fork has extras: PROVIDER_EXAMPLES.md, web/ dir, Cover.png

## Tasks for Replit Agent

### Task 1 — Update AI model references to claude-sonnet-4-6
Search all Python files in steps 00-17 for hardcoded model names:
```bash
grep -r "claude-\|gpt-\|model=" . --include="*.py" -l
```
Replace any old Claude model IDs (claude-3-*, claude-sonnet-3*) with `claude-sonnet-4-6`.
Update any OpenAI model references to also show the Claude equivalent.

### Task 2 — Add Step 18: Multi-Agent Team Coordination
Create `18-multi-agent-routing/` based on the three-man-team pattern:
- Planner agent (routes tasks to specialists)
- Executor agent (runs tool calls)
- Reviewer agent (verifies output quality)
- README.md explaining the pattern
- Runnable Python implementation using Anthropic API + claude-sonnet-4-6

### Task 3 — Update PROVIDER_EXAMPLES.md
Add examples for the latest providers:
- Anthropic claude-sonnet-4-6 (primary, recommended)
- OpenAI gpt-4.1 (if current)
- Groq llama-3.3-70b (fastest free tier)
- Google gemini-2.0-flash (free tier with 1M context)
- OpenRouter (aggregator, 200+ models)

### Task 4 — Verify All Steps Run
In each step directory, verify the main Python script runs without import errors:
```bash
python3 -c "import ast; ast.parse(open('main.py').read())" 
```
Fix any syntax errors or broken imports.

### Task 5 — README Update
Update the main README.md to reference:
- claude-sonnet-4-6 as the recommended model
- New Step 18 (multi-agent routing)
- Updated provider examples

## Star Count Note
The repo description says "50K stars in 2 hours" — this refers to the upstream
czl9707/build-your-own-openclaw repo, NOT our fork. Our fork currently has 0 stars.
Do NOT change the description — it's marketing copy for the upstream attribution.
