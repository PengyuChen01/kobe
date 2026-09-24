---
"@sma1lboy/rove": patch
---

Promoted IBM Bob from the shipped catalog to a built-in engine, so Rove reads its conversation rather than only launching it.

History, per-session token and context counts, and the sessions belonging to a worktree all come out of Bob's SQLite store; Settings → Engines now reports whether you are signed in, not who, because Bob keeps only an opaque token and Rove does not decode credential material. Workspace trust is pre-written the way it already is for Claude, Codex, Kimi and Copilot, so a parallel round no longer depends on the launch flag alone.

Hooks are the one thing Bob does not get: its bundle carries Claude's nested hook schema, but nothing fires from either the workspace or the global settings document on 2.0.5, so session identity comes from the history store keyed by worktree instead — the same origin Kimi uses.
