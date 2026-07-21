---
name: lovable-new
description: Create a new Lovable project from a one-line brief and return the editor and preview links.
---

# New Lovable project

Take the brief in the arguments and start a project.

1. Rewrite the brief as one concrete `create_project` prompt: the kind of app, the main screens, and the first action a visitor takes. Cut vague adjectives.
2. Call `create_project`. Omit `workspace_id` if the host renders the project widget; otherwise use the workspace named in the brief.
3. Wait for the first build, then read back `editor_url` and `preview_url`.
4. Look at the result through the `preview_url` or `get_diff` and confirm it matches the brief.
5. Reply with both links and one line on what was built.

If the brief is empty or too thin to build from, ask for the app's purpose and its first screen before calling `create_project`.
