---
name: lovable-deploy
description: Publish the current Lovable project and return the live URL after confirming the build.
---

# Deploy a Lovable project

Ship the current project.

1. Confirm the project with `get_project` and review the current state through `get_diff` or the `preview_url`.
2. Check that the requested change is actually in the build, not just reported as done.
3. If the project uses Lovable Cloud, confirm `get_database_status` shows a database.
4. Call `deploy_project`.
5. Reply with the live URL and the `preview_url`.

For analytics on a deployed project, use `get_project_analytics` and `get_project_analytics_trend`. To experiment off a live app without risking it, use `remix_project`.
