---
"@sma1lboy/rove": patch
---

Added IBM Bob (`bob`) to the shipped engine catalog, so it appears in the engine selector whenever `bob` is on your PATH and can be fanned out like any other engine: `rove api add --agents bob:3 --prompt "…"`.

Two things had to be right for a parallel round to work. Rove launches it as `bob chat --trust`, because `bob` alone only prints help and a fresh worktree otherwise stops the TUI on "Do you trust this folder?" — a round of nine would open nine dialogs with nobody to answer them. And the first message is pasted rather than appended to the command line: `bob chat` declares no positional argument and Bob 2.0.4 discards a stray one without an error, which would have left every sibling of a round sitting at an empty composer.

Activity badges come from a screen manifest captured against Bob Shell 2.0.4: the command-approval dialog, the folder gate and the browser sign-in wall all read as blocked, a streaming turn reads as working, and the resting composer as idle. The sign-in wall matters because an expired token leaves Bob on a bare spinner — without a rule for it a task that cannot run keeps whatever badge it had, and looks like it is resting.
