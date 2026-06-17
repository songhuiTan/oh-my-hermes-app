# AGENTS

This file is for AI agents (Hermes, Claude Code, Codex) working in this project.

## Project Overview

A full-stack application managed by Oh My Hermes CTO loop. AI agents autonomously handle issue triage, implementation, review, deployment, and monitoring.

## Build Commands

```bash
npm install
npm run dev
npm run build
npm run typecheck
```

## Architecture

TBD — designed via clarify-requirements workflow.

## Security Baseline

- Validate all input server-side
- Never trust client-provided identity, scope, or permissions
- Use Supabase RLS for row-level data isolation
- Store secrets in .env.local — never commit credentials
- No secrets in logs or error messages
- Follow OWASP Top 10

## Engine Guidance

- Complex multi-file changes, new features → Claude Code
- Quick targeted fixes, single-file changes → Codex
- Deploy, monitor, notify, schedule → Hermes
- UI/UX exploration before coding → Claude Design (human step)
- Not sure? Tell Hermes: run choose-engine

## Monitoring

- Health endpoint: /api/health
- Error tracking: Sentry
- Uptime: Uptime Kuma polling /api/health every 60s

## Deployment

- Platform: Vercel
- Production: main branch → automatic deploy
- Preview: feature branches → preview deployment

## Commit Conventions

- One commit per meaningful change
- Never commit .env.local or credentials
