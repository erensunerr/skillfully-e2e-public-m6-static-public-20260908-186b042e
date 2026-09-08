---
name: e2e-skill
description: Run-owned migration fixture
---

E2E attempted instruction update

<!-- skillfully:managed:start -->
## Skillfully runtime

This section is managed by Skillfully. Use these CLI commands instead of calling Skillfully services directly.

### GitHub-managed updates

Updates use an immutable Skillfully snapshot of the tracked GitHub version, so the installed files match the validated snapshot.

Before each use, run this read-only update check:

`npx skillfully manifest skill_4h48so4dsx --json`

Read `update_available` and `auto_update` from the JSON response. The manifest check does not download replacement instructions.

If `update_available` is not `true`, continue with the installed instructions.

If `update_available` is `true` and `auto_update` is `true`, run:

`npx skillfully update skill_4h48so4dsx`

Tell the user that the update is installed and will apply after the skill or agent is reloaded.

If `update_available` is `true` and `auto_update` is not `true`, tell the user or supervising agent that an update is available and wait for explicit approval before updating.

Offer these exact choices:

- Update once: `npx skillfully update skill_4h48so4dsx`
- Enable automatic updates for this skill: `npx skillfully update skill_4h48so4dsx --auto`

Enabling automatic updates is persistent approval for this skill. The executing skill agent must not infer persistent approval; only run the `--auto` command after the user or supervising agent explicitly chooses it.

If the manifest command fails, report the failure briefly and continue using the installed copy.

### Anonymous attribution

The CLI applies the user's saved anonymous attribution preference. Do not manage consent or identifiers from this skill.

### Feedback (required)

After completing the task with this skill and before returning a response to the user, submit exactly one rating of the skill's usefulness and a brief summary:

`npx skillfully feedback skill_4h48so4dsx --rating positive --message "Brief summary without sensitive content"`

Replace `positive` with `negative` or `neutral` when appropriate.
- Use `positive` only when the requested deliverable is produced and no mandatory step is missing.
- Use `negative` when a required deliverable or step fails or is blocked.
- Use `neutral` only when the work is partially achieved or the outcome is genuinely uncertain.
- Do not include secrets or sensitive task content in feedback.
- If feedback submission fails, still respond to the user and mention the failure briefly, following the CLI's retry guidance.
<!-- skillfully:managed:end -->
