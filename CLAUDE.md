## gstack (REQUIRED)

This project uses [gstack](https://github.com/garrytan/gstack) for all AI-assisted work.

**Before doing ANY work, verify gstack is installed:**

```bash
[ -d "$HOME/.claude/skills/gstack/bin" ] && echo "GSTACK_OK" || echo "GSTACK_MISSING"
```

If `GSTACK_MISSING` (for example in a fresh cloud session), install it first:

```bash
git clone --single-branch --depth 1 https://github.com/garrytan/gstack.git ~/.claude/skills/gstack
cd ~/.claude/skills/gstack && ./setup --team
```

Do not skip skills, ignore gstack errors, or work around a missing gstack.

### Always check the project

These checks are mandatory, not optional:

1. **New feature or larger change** — run `/autoplan` (or `/plan-eng-review`) before writing code.
2. **Bug** — run `/investigate` to find the root cause before fixing.
3. **Before every commit / push / PR** — run `/review` on the diff and fix what it finds.
4. **Anything touching auth, payments, user data, forms, APIs or dependencies** — run `/cso` (security audit).
5. **UI changes** — run `/design-review`; for a running site/staging URL run `/qa`.
6. **Before release** — run `/ship`, then `/document-release`.
7. Periodically (or when asked "check the project") — run `/health` for the overall code-quality dashboard.

Report the result of each check (what was found, what was fixed) in the final reply.

### Other rules

- Use the `/browse` skill from gstack for all web browsing; never use `mcp__claude-in-chrome__*` tools.
- Use `~/.claude/skills/gstack/...` for gstack file paths.

Available skills: /office-hours, /plan-ceo-review, /plan-eng-review, /plan-design-review,
/design-consultation, /design-shotgun, /design-html, /review, /deslop-shared-libs, /test-audit,
/ship, /eval-plan, /land-and-deploy, /canary, /benchmark, /browse, /connect-chrome, /qa, /qa-only,
/design-review, /scrape, /setup-browser-cookies, /setup-deploy, /setup-gbrain, /retro, /investigate,
/document-release, /document-generate, /codex, /cso, /autoplan, /plan-devex-review, /devex-review,
/careful, /freeze, /guard, /unfreeze, /gstack-upgrade, /learn, /health, /spec.
