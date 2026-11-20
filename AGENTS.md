# AI agent entry point — Tertalis Completion

This repository is the prospective Completion application workstream
and an imported snapshot of the Tertalis platform. There is not yet an
implemented Completion AppPack, VS Code extension or application launcher.
Do not present it as runnable end-user completion software.

## Orientation and ownership

1. Read [README.md](README.md) and [SETUP.md](SETUP.md).
2. Read the canonical
   [coordination index](https://github.com/EnterTheNameHere/Turnix/blob/actant-integration/ai-workflow/index.txt)
   and
   [protocol](https://github.com/EnterTheNameHere/Turnix/blob/actant-integration/ai-workflow/coordination-protocol.txt).
3. On that canonical `actant-integration` ref, review
   `ai-workflow/handoff/completion-thread.txt`,
   `ai-workflow/state/completion.txt`, current assignments and inbox,
   before acquiring any ownership claim.
4. Read relevant `docs/` and `design/` contracts for application
   lifecycles, externally initiated work, LLM execution, cancellation
   and shared host boundaries. Historic draft designs are not a
   substitute for current verified implementation behavior.

## Required boundaries

- This repository's `ai-workflow/` directory is an inherited
  historical copy, NOT a separately authoritative coordination inbox.
  The new repository does not create a new Coordinator.
- The Completion workstream owns Completion-specific application logic
  and the VS Code extension. It does not own the shared platform
  `backend/` or reusable first-party Packs.
- Completion must not independently launch or own a competing shared
  inference authority. Route reusable runtime/provider/resource gaps
  through the canonical Integration coordination process.
- Distinguish VS Code observations from platform application operations:
  unsaved editor content is supplied by the extension, and source files
  are data, not CodeEntries just because they contain code.
- Adopt new platform revisions only through authorized verified
  integration; failed adoption leaves the old pinned revision intact.
- Preserve history and accepted evidence. No destructive branch
  actions, force pushes or unapproved failure tests.

## Setup and verification

From the repository root on Windows:

```powershell
.\setup.bat
.\python-embedded\python.exe -X frozen_modules=off -m pytest tests
```

These are platform setup and test commands, not application launch
commands. No Completion application-specific setup or `run.bat` exists
at present. Report exact refs, checks actually performed and any
unverified assumptions. Follow the canonical handoff/finish barrier.
