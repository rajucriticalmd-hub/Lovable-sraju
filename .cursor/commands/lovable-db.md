---
name: lovable-db
description: Provision or inspect a project's Lovable Cloud database and run read queries safely.
---

# Lovable Cloud database

Work with the current project's database based on the request in the arguments.

1. Call `get_database_status`. If there is no database and one is needed, call `enable_database`, wait 30 to 60 seconds, then re-check status.
2. For inspection, run `query_database` with the columns you need and a LIMIT while exploring. Report what you find, with row counts.
3. For a write or a destructive statement, show the exact SQL and confirm it is wanted before running it. Do not run DROP, DELETE, TRUNCATE, or ALTER unless that was the explicit request.
4. For schema or data-model changes the app depends on, describe them to the Lovable agent with `send_message` instead, so the code and database stay in sync.

Treat every query as production access, because it is.
