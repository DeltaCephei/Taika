# Shared Context — VPS ↔ MacBook Bridge

This folder is the sync point between Eliot's VPS agent team (Taika + crew) and his MacBook agents (Claude Code local).

## How It Works
- **VPS team** pushes updates here after each session and via daily auto-sync
- **MacBook agents** read from here to know what the VPS team has been doing
- **GitHub** is the transport layer — both sides already sync this repo

## Files

| File | What It Is | Updated |
|------|-----------|---------|
| `MEMORY.md` | Taika's long-term memory — key facts, lessons, project status | As needed |
| `daily-log.md` | Rolling log of recent days — conversations, decisions, tasks done | Each session |
| `active-projects.md` | Current status of all projects with next steps | Each session |
| `README.md` | This file | Rarely |

## For MacBook Agents

Add this to your agent instructions:

> Before starting any work session, read the files in the `Taika/shared/` folder (synced via GitHub from the VPS team). This contains:
> - What the VPS team has done recently (`daily-log.md`)
> - Current project status and next steps (`active-projects.md`)  
> - Long-term context and key decisions (`MEMORY.md`)
>
> If you do significant work, update `daily-log.md` with what you did so the VPS team stays informed.

## For VPS Team (Taika)

At the end of each meaningful session:
1. Update `daily-log.md` with today's conversations and decisions
2. Update `active-projects.md` if project status changed
3. Push to GitHub

This is automated in Taika's session-end routine.
