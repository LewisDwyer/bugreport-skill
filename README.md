# Bug Report Skill

A [Claude Code skill](https://docs.anthropic.com/en/docs/claude-code/skills) that helps you write structured bug reports in Ritza's standard format.

## What it does

When you encounter a bug, invoke the skill and it walks you through writing a clear, reproducible bug report with four sections:

- **Summary** — a one-line description of the issue
- **What I did** — step-by-step reproduction instructions
- **What I expected to happen** — the correct behavior
- **What actually happened** — the actual broken behavior, including errors and screenshots

If you give partial info, it shows a draft with gaps marked so you know exactly what's still needed.

Once the report is complete and approved, it auto-publishes to [drafts.cc.ritza.co](https://drafts.cc.ritza.co) (HedgeDoc) and reminds you to share the link in the relevant Slack channel.

## Example output

```markdown
# 500 error on sign in

Getting a 500 error when trying to sign in

## What I did

1. Went to the login page at https://app.example.com/login
2. Clicked "Sign in"
3. Entered my username and password
4. Clicked "Submit"

## What I expected to happen

I expected to be logged in and redirected to my dashboard.

## What actually happened

I saw a white page with `HTTP 500: Server error`.
```

## Installation

Copy the skill into your Claude Code skills directory:

```bash
cp -r bugreport-skill ~/.claude/skills/bugreport-skill
```

Or clone this repo directly:

```bash
git clone https://github.com/LewisDwyer/bugreport-skill.git ~/.claude/skills/bugreport-skill
```

## Usage

The skill triggers automatically when you mention logging a bug, reporting a bug, filing a bug report, or writing up an issue. You can also invoke it explicitly with `/bugreport`.
