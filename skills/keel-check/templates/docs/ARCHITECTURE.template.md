> Tracker: TICKET-# (name of project)
Verified: YYYY-MM-DD (last as-built review or release; the only date to trust)

## Architecture at a glance
(For a reader who has forgotten the project; at most about 20 lines. Keep it true to the code; no history.)
- What it is: (1 to 3 sentences)
- Main parts: (the components and what each one does, such as UI, API, worker, database, external services)
- How they connect: (the main flow of data or control, in a list or a diagram link)
- Where to start reading the code: (entry points and the folders that matter most)
- Key decisions: (the 3 to 5 that shape everything, each linked to docs/decisions/)
- Related docs: docs/DEVELOPMENT.md (run it), docs/FEATURES.md (use it)

## Stack
## Folder layout
## Commands
(Build, run, test, and lint commands added during development. Commands from the ticket stay in README.md.)
## Data model & APIs
(Design of the data model and of any interfaces other programs use. Include migrations, personal data, and retention, or say the project has none. How to use an interface goes in docs/FEATURES.md; link a generated reference here or there if one exists.)
## Auth & security
## Hosting & deployment
## Environment facts
(Facts the AI cannot learn from the code, 1 line each: staging and production URLs, folders or services never to touch, ports, accounts by name, and where things run. Names only, never secrets; values go in .env.example as names.)
## Operations
(Logging, error handling, backups and retention, monitoring, and what to do when it fails. Split to docs/RUNBOOK.md when this passes a page.)
### Known traps
(Lasting surprises and workarounds, moved here from HANDOFF.md: what, why, and how to avoid it.)
## Testing
- What must be tested: (e.g., business logic, API endpoints, key user flows)
- Tools: (e.g., the project's test framework; a saved script only if there is no framework)
- Minimum bar: (e.g., new code ships with tests; targeted tests and the docs check pass for each change; a full regression passes before each release)
- Docs check: (`...`). The list of checks is in the script's header comment. Runs with every change; writes `test-results/docs.md`.
- Full regression command: (`...`)
- Stronger checks: (the developer's answer to the rule 9 question: "not used", "what-if cases", or "what-if cases and mutation testing" with the tool and command)
### Area map
(One row per area. Use the feature groups from SPEC.md as the areas. Read this map before you search the code. Reading the files near your change is normal; use the map to find what is not near, such as the areas that use your code. In Depends on, name the shared libraries and other areas this area uses, most of all the ones that are not obvious from its folder. Update the map when code, tests, or areas change. Confidence: High = the developer reviewed the row; Inferred = from code, not yet reviewed; Low = incomplete read, and the row says where reading stopped.)
| Area | Code (folders or files) | Entry points | Tests | Command (this area only) | ACs | Depends on | Confidence |
|---|---|---|---|---|---|---|---|
| (Login) | (src/auth/) | (src/auth/login.js) | (tests/login.test.js) | (`npm test -- login`) | (AC-1, AC-2) | (Data model, Auth) | (High) |
| Docs | (scripts/check-docs.js) | | | (`node scripts/check-docs.js`) | | | High |
## Links to diagrams
