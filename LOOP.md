# Loop Configuration — Minimal Triage (Claude Code)

## Active Loops

| Pattern | Cadence | Status | Command |
|---------|---------|--------|---------|
| Daily Triage | 1d | L2 assisted-fix (human-approved PR) | `/loop 1d Run $loop-triage in L2 mode` |

## Human Gates

- L2: auto-fix allowed in isolated worktree, but merge requires human approval of the PR
- All high-risk paths: human review required (see docs/safety.md denylist)

## Worktrees

- Use `isolation: worktree` when spawning implementer sub-agents (L2+).
- One worktree per fix attempt; discard after verifier REJECT.

## Connectors (MCP)

- MCP optional for L1 report-only loops.
- For L2+: GitHub MCP to read CI/issues; scope connectors to read + comment only until trusted.

## Budget

- Max sub-agent spawns per run: 2 (L2 — 1 Implementer + 1 Verifier, different agent/instructions, never self-graded)
- Review STATE.md daily

## Links

- Pattern: [daily-triage](../../patterns/daily-triage.md)
- Checklist: [loop-design-checklist](../../docs/loop-design-checklist.md)