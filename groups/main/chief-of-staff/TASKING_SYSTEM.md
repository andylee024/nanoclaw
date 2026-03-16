# Tasking System

This is the translation layer from raw asks to the real systems of record.

The goal is not to create a second project manager inside Markdown. The goal is
to make sure every request lands in the right operational home.

## Design Goals

- Let the user drop in raw asks quickly
- Make work visible and easy to audit
- Keep active work small and high signal
- Turn vague ideas into clear next actions
- Separate real commitments from low-value noise
- Support both human reviews and NanoClaw scheduled follow-ups
- Avoid duplicate state across Markdown, Linear, Calendar, and Claw Fitness

## Item Model

Every captured item should have:

- `id`: stable identifier such as `COS-001`
- `type`: `goal`, `commitment`, `project`, `ops`, or `decision`
- `status`: workflow state
- `owner`: `andy`, `user`, `external`, or shared
- `area`: work, relationships, exercise, money, travel, admin, style, or other
- `outcome`: what done looks like
- `next_action`: the next concrete move
- `due` or `review`: when it matters next
- `approval`: whether user approval is required before execution

Optional fields:

- `priority`
- `blocker`
- `links`
- `notes`

## Status Workflow

- `inbox`: captured, not clarified yet
- `ready`: scoped and ready to work
- `in_progress`: actively being worked
- `waiting_on_user`: blocked on the user's answer or approval
- `waiting_on_external`: blocked on another person, vendor, or timing event
- `scheduled`: parked for a future date, check-in, or automated review
- `done`: completed and logged

## Rules

- Every non-done item must have exactly one next action
- Every `in_progress` item must have a current owner
- User-facing decision load should stay small
- If an item can be finished safely, finish it instead of bouncing it back
- If approval is required, narrow the ask to the smallest decision possible
- If work repeats, turn it into a playbook or scheduled review
- Once an item matters beyond scratch capture, move it into the proper system of
  record

## Views We Should Operate From

### Today

- urgent decisions
- today's commitments
- items that unblock work, relationships, or exercise

### This Week

- active projects
- upcoming trips, dates, gifts, replacements, and social obligations

### Waiting On

- external replies
- pending approvals
- bookings or deliveries in flight

### Decision Queue

- anything that needs a user call
- should be short, concrete, and recommendation-led

### Backlog

- useful but not active
- reviewed weekly, not daily

## Relationship To NanoClaw

- `Linear` is the canonical live board
- `Google Calendar` is the canonical time system
- `Claw Fitness` is the canonical workout execution/log
- `WORKBOARD.md` is only local intake, migration, and review scratch space
- NanoClaw scheduled tasks should be used for recurring reviews, reminders,
  waiting-on follow-ups, and future check-ins

## Intake Conventions

The user should be able to say things like:

- "Handle this trip"
- "I need a gift for Sam"
- "Help me replace my shoes"
- "Figure out my taxes"
- "I want to date more this month"

The chief of staff should convert that into one or more well-formed items on
the correct system.

Examples:

- multi-step follow-up -> `Linear`
- real scheduled plan -> `Google Calendar`
- workout logging or programming -> `Claw Fitness` / `Train`
- durable preference or playbook -> local Markdown

## First Upgrade Path

Once the workflow feels stable:

- add better recurring issue templates in `Linear`
- add playbooks for common chief-of-staff flows
- add richer local docs for people, venues, and recurring checklists
- build automation only where the manual loop is already working
