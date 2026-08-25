# RevenueForge — Claude Code Context

## Always-Load Context

@project-control/project_state.json
@knowledge/architecture.md

---

## What This Project Is

Revenue-engine automation for $5-15m knowledge businesses. Planning stage - documents only, no code.

**Tech stack:** None - planning stage
**Database:** none
**Auth:** none
**Handles payments:** false
**Has AI endpoints:** false

## Project State File

All phase tracking, decisions, milestones, and resume points live at:
`project-control/project_state.json`

Read this file at the start of every session. It tells you exactly where to pick up.

---

## ARCHITECTURE RULES — NON-NEGOTIABLE

These rules are enforced by hooks and must never be violated, even if it feels more
convenient to break them. If you find yourself about to break one, STOP and find the
correct pattern.

### Module Boundaries

```
/routes         → HTTP handlers ONLY. Extract params. Call one service function. Return response.
                  ZERO business logic. ZERO database queries. ZERO external API calls.

/services       → All business logic. Orchestrates db/ calls and external APIs.
                  This is where decisions are made and data is transformed.

/db             → ALL database queries live here and NOWHERE ELSE.
                  Functions take plain Python/TypeScript values, return plain values.
                  No HTTP context. No request/response objects.

/models         → Data schemas, Pydantic models, Zod types, TypeScript interfaces.
                  No logic. Only shape definitions.

/middleware      → Auth verification, rate limiting, logging, request validation.
                  Applied at the router level, not inline in handlers.

/utils          → Pure functions with zero side effects.
                  No DB access. No HTTP calls. No state.
```

**Before writing any function, ask:** which directory does this belong in?
**If you write a DB query in a route file:** stop, move it to /db/, call it from there.
**If you write business logic in a route file:** stop, move it to /services/, call it from there.

### File Size Limits

- **300 lines maximum per file.** If you hit this limit while adding code, you must
  extract before continuing. No exceptions, no "I'll refactor later."
- **40 lines maximum per function.** Long functions are always decomposable into
  smaller functions with clear names.
- **One responsibility per file.** A file that handles users AND payments AND emails
  is three files waiting to happen.

### DRY Enforcement

Before writing any new function, run a mental (or literal) grep for similar logic that
already exists in the codebase. If it exists: call it. If it almost fits: extend it.
Only write new code when nothing similar exists.

---

## SECURITY REQUIREMENTS — NON-NEGOTIABLE

Every one of these must be satisfied before any endpoint ships to production.

### Authentication
- Every HTTP endpoint that is user-facing MUST verify auth before executing logic.
  Use middleware/Depends — not inline checks scattered in handlers.
- No endpoint is public by default. Explicit opt-out required with a comment explaining why.


### Stripe Webhook Verification
- Every handler that receives Stripe webhook events MUST call `construct_event()` (Python)
  or `constructEvent()` (Node.js) before accessing any event data.
- The webhook secret MUST come from an environment variable (STRIPE_WEBHOOK_SECRET).
- Never trust the raw payload without signature verification. This is how accounts get
  fraudulently upgraded with a single curl command.



### AI Endpoint Protection
- Every endpoint that triggers an AI API call MUST have both:
  1. Authentication (verified before the AI call)
  2. Rate limiting (slowapi @limiter.limit or express-rate-limit)
- Auth alone is not enough. One valid token can hammer an unprotected endpoint and
  generate surprise $400+ bills.
- Set a hard spending cap in the Anthropic/OpenAI dashboard. This is the last line of defense.



### Supabase RLS
- Every table created MUST have RLS enabled: `ALTER TABLE public.<name> ENABLE ROW LEVEL SECURITY;`
- Never use `USING (true)` or `WITH CHECK (true)` policies. These disable all protection.
- For service_role-only apps: enable RLS, add no policies (service_role bypasses RLS by design).
- For user-facing apps: policies must reference `auth.uid()`.


### Secrets
- Zero hardcoded credentials anywhere in source code.
- All secrets live in environment variables.
- `.env` is gitignored from day one, before the first commit.
- Any key that touches source control is considered compromised and must be rotated immediately.

---

## CODE QUALITY RULES

### Refactor Cadence
Every 5 features added, run one cleanup pass:
- Find the three most egregious architecture violations
- Find any file approaching 300 lines
- Find any duplicated logic
- Fix these before continuing feature work

This is not optional. Technical debt compounds faster than feature value.

### The Right Order (Non-Negotiable)
1. Define what you're building in plain English
2. Identify which modules it touches
3. Write the function signatures (no implementation)
4. Implement, following module boundaries
5. Test the happy path + one failure path

Never start from step 4. Code written without understanding the shape of the solution
first is always spaghetti.

---

## TECH STACK SPECIFICS

This repo holds planning documents only. Any build gets its own repo.

---

## VERIFICATION CHECKLIST (before declaring any feature done)

- [ ] No business logic in route handlers
- [ ] No DB queries outside /db/
- [ ] No file exceeds 300 lines
- [ ] All new endpoints have auth
- [ ] No hardcoded secrets

- [ ] Stripe webhook handlers call construct_event


- [ ] AI endpoints have rate limiting


- [ ] New tables have RLS enabled

