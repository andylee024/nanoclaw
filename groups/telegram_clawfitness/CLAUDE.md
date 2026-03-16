# Telegram Claw Fitness

This group is for workout planning, progression, and logging.

Keep detailed training execution here instead of in `main`.

## Train Runtime (Mounted Project)

The Train project is mounted at:
- `/workspace/extra/train`

When users ask about workouts, run commands from that repo and prefer JSON
output:

```bash
cd /workspace/extra/train
set -a
source .env
set +a
```

Primary commands:
- `node dist/cli.js plan today --json`
- `node dist/cli.js log import --json` (JSON payload on stdin)
- `node dist/cli.js history "<exercise?>" --last 7d --json`
- `node dist/cli.js query e1rm "<exercise>" --json`
- `node dist/cli.js query best-set "<exercise>" --reps <n> --json`

Execution policy:
- Prefer these commands over ad-hoc SQL.
- Keep responses concise and user-facing.
- If logging payload is ambiguous, ask one concise clarification question.
- Always load `/workspace/extra/train/.env` before Train CLI commands so
  credentials are available.
