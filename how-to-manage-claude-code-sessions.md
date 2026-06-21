# How to manage Claude Code sessions

**Published:** Feb 27, 2026

Source: https://remarkablemark.org/blog/2026/02/27/how-to-manage-claude-code-sessions/

---

## Overview

This guide explains how to manage Claude Code sessions through the command line, covering four key operations: listing, resuming, clearing, and deleting sessions.

## List

Claude Code keeps session data in `~/.claude/projects/`. To view available sessions:

```
ls ~/.claude/projects/
```

Sessions are stored as JSON Lines files. Find them using:

```
find ~/.claude/projects -type f -name '*.jsonl'
```

Display a sample session:

```
cat $(find ~/.claude/projects -type f -name '*.jsonl' | head -n 1)
```

## Resume

Reopen an existing session with:

```
claude --resume
```

## Clear

Clear conversation history within an active session:

```
/clear
```

Note: This command removes context but preserves the session file itself.

## Delete

Remove all project sessions:

```
rm -rf ~/.claude/projects/
```

Delete sessions from a specific project:

```
rm -rf ~/.claude/projects/<PROJECT>/*.jsonl
```

*(Substitute your actual project path for `<PROJECT>`)*

---

For more information, visit the [Claude Code repository](https://github.com/anthropics/claude-code).
