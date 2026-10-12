---
name: savvy-flow
description: Run a task through a disciplined workflow - understand the request and codebase, plan, implement in small steps, verify with the project's own checks, and report honestly. Use when the user invokes /savvy-flow or asks for a careful, end-to-end take on a coding task.
argument-hint: "<task description>"
---

# Savvy Flow

Task: $ARGUMENTS

If no task was given, ask the user for one in a single short question and stop.

Work through the five stages below in order. Keep each stage proportionate to
the task: a one-line fix needs a sentence of planning, not a document.

## 1. Understand

- Restate the goal in one or two sentences, including what "done" means.
- Read the code the task touches and the code that calls it. Find the project's
  conventions (naming, error handling, test layout) and its fast checks
  (lint, format, typecheck, unit tests) from config files, scripts and README.
- If a decision is genuinely the user's to make and cannot be settled from the
  request, the code, or a sensible default, ask now. Otherwise pick the default
  and note it.

## 2. Plan

- List the concrete changes, file by file, in the order you will make them.
- Name the checks you will run to prove the change works, and any test you
  will add.
- For anything that is hard to reverse (deleting data, rewriting history,
  publishing, external side effects), say so and get confirmation first.

## 3. Build

- Make the smallest change that meets the goal. Match the surrounding code's
  style and comment density; don't widen scope.
- Work in small steps and re-read each edit before moving on.

## 4. Verify

- Run the checks named in the plan. For a bug fix, reproduce the bug first,
  then show it gone.
- Re-read the full diff adversarially: what would a reviewer or CI reject?
  Fix it before finishing.
- If a check fails and you cannot fix it, stop and report it - never skip,
  disable or weaken a test to get green.

## 5. Report

Finish with a short summary:

- **What changed** - the files and the behaviour, in plain words.
- **How it was verified** - the commands run and their results.
- **Open items** - assumptions made, anything skipped, and follow-ups.

Report outcomes faithfully: if something was not verified, say so.
