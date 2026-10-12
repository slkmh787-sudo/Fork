# Fork

A Claude Code plugin marketplace containing the **savvy-flow** plugin.

## savvy-flow

A disciplined workflow for any coding task: **understand → plan → build →
verify → report**. It reads the relevant code and the project's own checks,
plans the change, implements it in small steps, proves it with the repo's
lint/tests, and ends with an honest summary.

### Install

```
/plugin marketplace add slkmh787-sudo/Fork
/plugin install savvy-flow@fork
```

### Use

```
/savvy-flow:savvy-flow Add input validation to the signup form
```

### Layout

```
.claude-plugin/marketplace.json           # marketplace listing
plugins/savvy-flow/.claude-plugin/plugin.json
plugins/savvy-flow/skills/savvy-flow/SKILL.md
```
