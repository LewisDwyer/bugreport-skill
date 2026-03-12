---
name: bugreport
description: Write a bug report in Ritza's standard format (Summary, What I did, What I expected, What actually happened). Use this skill whenever the user wants to log a bug, report a bug, file a bug report, write a bug report, document an issue they found, or mentions encountering a bug they want to write up — even if they don't use the exact phrase "bug report".
---

# Bug Report Skill

You help users write clear, structured bug reports following Ritza's standard format. The goal is to capture enough context that someone else can reproduce and fix the issue without a back-and-forth conversation.

## The format

Every bug report has exactly four parts:

```
<Summary — a one-line description of the bug>

## What I did

<Step-by-step reproduction instructions>

## What I expected to happen

<The correct/intended behavior>

## What actually happened

<The actual broken behavior, including error messages and screenshots>
```

## How to gather information

The user might give you everything upfront, or they might just say "I found a bug." Either way, your job is to fill in all four sections.

1. **Check what the user already provided.** If they described the bug in their message, extract as much as you can into the four sections. Don't re-ask for information they've already given you.

2. **Show a draft with gaps.** Even if information is missing, show the user a partially filled-in report using the exact Ritza format. Fill in what you know and mark missing sections with a short prompt like `[Please describe the steps you took]`. This helps the user see exactly what's needed and where their info will go. For example:

   ```
   Login page broken on FusionAuth docs

   ## What I did

   [Can you walk me through what you did before hitting this issue? E.g. which page, what you clicked]

   ## What I expected to happen

   [What should have happened instead?]

   ## What actually happened

   [What did you see? Any error messages, blank screens, or unexpected behavior? Screenshots help a lot here]
   ```

3. **Encourage specifics.** Good bug reports include:
   - Exact steps to reproduce (not "I clicked around and it broke")
   - Exact error messages (copy-pasted, not paraphrased)
   - Screenshots if the user has them
   - Browser/OS/environment details if relevant
   - URLs where the issue occurred

4. **Keep the summary crisp.** It should read like a subject line — e.g., "500 error when signing in with SSO" not "There's a problem with the login page."

## Output

Whether the report is complete or still a draft with gaps, always use the exact Ritza format with the `## What I did` / `## What I expected to happen` / `## What actually happened` headers.

Once you have a complete report (all four sections filled in), produce the final formatted bug report as a clean markdown block the user can copy.

Always include the posting reminder — even when still gathering info, so the user knows the workflow:

> When this report is ready, post it to https://drafts.cc.ritza.co and share the link in the relevant **#ritza-&lt;customer&gt;** Slack channel.

## Example

Here's what a finished bug report looks like:

```
Getting a 500 error when trying to sign in

## What I did

1. Went to the login page at https://app.example.com/login
2. Clicked "Sign in"
3. Entered my username and password
4. Clicked "Submit"

## What I expected to happen

I expected to be logged in and redirected to my dashboard.

## What actually happened

I saw a white page with `HTTP 500: Server error`. Screenshot attached below.

![500 error screenshot](screenshot.png)
```
