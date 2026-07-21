---
name: lovable-iterate
description: Send a change to an existing Lovable project's agent and verify it in the diff.
---

# Edit a Lovable project

Apply the change described in the arguments to the current project.

1. Confirm the target project with `list_projects` or `get_project`.
2. If the change is open-ended or risky, run `send_message` with `plan_mode=true` and settle the approach first.
3. Send the change as one focused `send_message`. Name the specific screen and element. Attach an image if it is visual.
4. Read the reply with `get_message`, then `get_diff` to see what actually changed.
5. If it is off, send a follow-up pointing at the specific problem rather than restating everything.
6. Reply with what changed and the `preview_url`.

If more than one project could be the target, ask which one before sending anything.
