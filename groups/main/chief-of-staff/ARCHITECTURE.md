# Chief Of Staff Architecture

This is the intended layering for the system.

## Layer 1: Upstream Core

`upstream/main` is vendor code.

Treat it as the clean base:

- orchestration
- containers
- SDK wiring
- official skills
- generally useful platform features

Do not put personal operating rules here unless there is no better place.

## Layer 2: Fork Runtime

The fork branch is for durable capability changes that are worth carrying as
code:

- channels such as Telegram or WhatsApp
- Google Calendar or Gmail access
- container runtime adjustments
- reusable prompt/runtime behavior that is broader than one local workflow

Rule: if the change would still make sense for a future clean reinstall, it can
live here.

## Layer 3: Local Operating System

This folder and other group folders are where ongoing personal adaptation
should happen.

This is where to keep:

- chief-of-staff operating rules
- life-area strategy
- venue lists
- people notes
- approval thresholds
- recurring review formats
- taste and preferences
- domain playbooks

Rule: if the change is about *you* rather than *NanoClaw*, put it here.

## Layer 4: External Systems Of Record

Do not duplicate live operational state across multiple places.

- `Linear`: active work, follow-up, recurring routines, decisions
- `Google Calendar`: real time commitments
- `Claw Fitness` + `Train`: actual workout plan and logging
- local markdown: durable context and playbooks

Markdown should explain how to operate the systems above, not compete with
them.

## Main Group Role

The `main` group is the executive layer.

It should:

- prioritize
- coordinate across domains
- notice conflicts
- prepare decisions
- maintain durable guidance

It should not become the detailed execution log for every domain.

## Specialist Runtime Role

Use specialist groups and tools when a domain already has a stronger operating
surface.

Current split:

- `main`: chief of staff, cross-domain planning, decisions, admin
- dedicated training runtime (`telegram_clawfitness`,
  `whatsapp_clawfitness`, or equivalent): training execution and workout logs
- `Google Calendar`: schedule
- `Linear`: work instances and recurring routines

## Messaging Topology

- Keep exactly one privileged `main` chat for chief-of-staff work and admin.
- Add specialist chats when a domain benefits from isolated memory, prompts,
  and tools.
- Training should live in its own dedicated chat rather than in `main`.
- For Telegram, use separate chats rather than topics because routing is keyed
  by `chat.id`, not by thread.

## Update Discipline

To keep upstream updates clean:

1. Keep personal rules and preferences in group docs, not in tracked core
   source files.
2. Keep fork-level code changes limited to real capabilities.
3. Do not leave long-lived WIP mixed into the branch you use for upstream
   merges.
4. Before pulling upstream, either commit the capability work or move it to a
   feature branch.
5. After merging upstream, re-apply only the code changes that still matter.

## Decision Rule

When deciding where a change goes, ask:

1. Is this a product capability or a personal operating rule?
2. Is there already a system of record for this?
3. Will this create duplicate state if I write it here?
4. Is this something I want to survive a clean reinstall automatically?

If the answer is "personal rule" or "duplicate state", it belongs in local
docs, not core code.
