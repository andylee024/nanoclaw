# Chief of Staff System

This folder is the local operating system for the main chief-of-staff group.

The point of this folder is to absorb most personal adaptation so upstream
NanoClaw code can stay relatively clean.

## Systems Of Record

- `Linear` is the live tracker for active work, follow-up, recurring reviews,
  and user decisions
- `Google Calendar` is the source of truth for time, dates, travel, classes,
  and commitments
- the dedicated training runtime (`telegram_clawfitness`,
  `whatsapp_clawfitness`, or equivalent) plus the mounted `Train` project are
  the source of truth for workout execution, progression, and logging
- this folder is the source of truth for durable preferences, playbooks,
  architecture, and review guidance

## File Map

- `CHARTER.md`: operating manual and decision rules
- `ARCHITECTURE.md`: repo layering, update discipline, and system boundaries
- `LINEAR.md`: how the live board should be used
- `CADENCE.md`: daily, weekly, and monthly operating rhythm
- `PROFILE.md`: durable user preferences and approval thresholds
- `TASKING_SYSTEM.md`: translation layer from raw asks into tracked work
- `WORKBOARD.md`: local intake and migration scratchpad, not the canonical
  live board
- `areas/ATHLETE.md`: how workout support should be organized
- `areas/SOCIAL.md`: dating, friends, family, and social logistics
- `areas/CALENDAR.md`: calendar ownership, planning rules, and review process

## Organizing Rule

If a change is mostly about:

- preferences
- operating rules
- routines
- playbooks
- domain context
- venues, people, or taste

put it in this folder.

If a change is mostly about:

- a new integration
- a new channel
- a new tool
- container/runtime behavior
- a reusable product capability

handle it as a fork-level code change or skill.
