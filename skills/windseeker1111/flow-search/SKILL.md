---
name: flow-search
description: Deep web research using Claude's native search tool. Use for comprehensive research, market analysis, competitor intelligence, or when standard search isn't enough. Free from the Flow team.
metadata: {"clawdbot":{"emoji":"🔍"}}
---

# FlowSearch — Deep Web Research

Power web research using Claude CLI. Use this when you need:
- Deep research requiring synthesis across multiple sources
- Market and competitor analysis
- Finding recent news, pricing, and trends
- Any query where quick search isn't cutting it

## Prerequisites

- [Claude Code CLI](https://docs.anthropic.com/en/docs/claude-code) installed and authenticated
- `CLAUDE_CODE_OAUTH_TOKEN` set in your environment (from `claude auth login`)

## Installation

```bash
npx clawhub@latest install flow-search
cd ~/.openclaw/skills/flow-search
npm install
```

## Usage

### Quick Search
```bash
npx tsx search.ts "Kling AI Pro plan pricing 2026"
```

### Deep Research
```bash
npx tsx search.ts --deep "AI video generation market analysis"
```

### In Code / Skills
```typescript
import { claudeSearch, claudeResearch } from "./search.ts";

// Quick search
const result = await claudeSearch("What is Kling AI pricing?");
console.log(result.answer);

// Deep research with specific questions
const research = await claudeResearch("AI video market", [
  "Who are the top players?",
  "What are typical pricing models?",
  "What's the market size?"
]);
```

## When to Use

| Use FlowSearch | Use Brave/Basic Search |
|----------------|----------------------|
| Deep research | Quick facts |
| Multi-source synthesis | Single answer needed |
| Market analysis | Simple lookups |
| Competitor intelligence | Basic info |

## Output Format

**Quick search** returns a direct answer with sources.

**Deep research** returns:
- Summary (2-3 sentences)
- Key Findings (bullet points)
- Detailed Analysis
- Sources with URLs

## Notes

- Requires Claude Code CLI with an active Max subscription for best results
- Quick search: ~15-30 seconds
- Deep research: ~60-180 seconds
- Works with any Claude Code auth method (`CLAUDE_CODE_OAUTH_TOKEN` or browser login)
