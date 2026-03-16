# Linear Operating Spec

This is the live work model for the chief-of-staff system.

## Team

- Team name: `Chief-of-Staff`
- Team key: `COS`

The board is reachable from this environment through the Linear API.

## Principle

Linear is the single live tracker for chief-of-staff work.

Use it for:

- commitments
- active projects
- recurring routines
- decisions that need user review

Do not create a second local task tracker in the repo.

## Statuses

The current workflow is:

- `Backlog`
- `Todo`
- `In Progress`
- `Needs review`
- `Done`
- `Canceled`
- `Duplicate`

## Status Meanings

Use the statuses like this:

- `Backlog`: valid work, but not committed yet
- `Todo`: committed and ready to move
- `In Progress`: actively being worked by Andy or actively in motion
- `Needs review`: blocked on user review, approval, or decision
- `Done`: resolved
- `Canceled`: intentionally dropped
- `Duplicate`: merged into another issue

## Labels

Current operating labels:

- `craft`
- `dating`
- `athlete`
- `F&F`
- `admin`
- `finances`

There are also default Linear labels like `Feature`, `Improvement`, and `Bug`.
Ignore those for chief-of-staff work unless a future workflow clearly needs
them.

## When To Create An Issue

Create a Linear issue when:

- the work will take more than one step
- the work should be revisited later
- the work involves coordination, approval, or follow-up
- the work is recurring
- the work is important enough that it should be visible and auditable

Do not create an issue when:

- the answer can be handled fully in one response
- the work is trivial and does not need tracking

## Issue Shape

For now, every issue should try to answer these questions in the description:

1. What is the outcome?
2. Why does it matter?
3. What is the next step?
4. What does Andy own?
5. What, if anything, needs user review?

## Title Style

Prefer short outcome-oriented titles.

Good:

- `Plan Austin trip with Callum and Tanner`
- `Monthly financial review for April`
- `Replace gym shoes`
- `Find 3 strong date spots in Silver Lake`

Bad:

- `Trip`
- `Money`
- `Shoes`
- `Dating stuff`

## Review Conventions

`Needs review` should be reserved for real user decisions or approvals.

If an issue is there, Andy should present:

- a recommendation
- the minimum context needed
- the exact decision required

The goal is to reduce the user's decision load, not just pass work back.

## Recurring Work

Recurring workflows should usually be represented as repeating Linear issues.

First likely recurring issues:

- daily review
- inbox triage
- monthly financial review
- birthday / gift radar

Each recurring issue should be paired with a reusable skill once the workflow is
stable enough.

## First Skills To Map To Linear

- `cos-daily-review`
- `cos-inbox-triage`
- `cos-plan-trip`
- `cos-monthly-financial-review`

The rule is simple:

- Linear tracks the work instance
- the skill is the execution playbook

For board mutations, use the `cos-linear` skill.

## Suggested Next Improvements

Not required now, but likely useful later:

- add a label for `recurring`
- add a label for `waiting-on-external`
- add lightweight issue templates for trips, purchases, and reviews
