# Tertalis Completion

**Status: planned application; Completion is not yet implemented.**

Tertalis Completion is intended to bring AI-assisted code completion to
VS Code through a Tertalis AppPack. The editor extension will provide
editor-authoritative context, such as unsaved buffers, cursor position,
selections and open editors. Tertalis should own application execution,
model access and shared resource orchestration, rather than the extension
acting as an independently hosted model authority.

**No Completion AppPack, VS Code extension, editor request transport,
or functional code-completion launcher exists here yet.** This repository
currently contains the existing Tertalis platform working tree, reusable
facilities, tests and the Completion development workstream's historic
planning and coordination material.

## Development environment

On Windows, clone the repository and prepare the platform:

```powershell
git clone https://github.com/Tertalis/Tertalis-Completion.git
cd Tertalis-Completion
.\setup.bat
```

This root setup initializes Tertalis internals and the repository-local
Python and tools. It does **not** install a Completion extension, launch a
model server or set up an application. There is not yet a separate Completion
application setup or run script.

See [SETUP.md](SETUP.md) for the real Windows requirements and the
explicit Python 3.14 fallback. After setup, the existing **platform**
tests can be invoked with:

```powershell
.\python-embedded\python.exe -X frozen_modules=off -m pytest tests
```

This command is not a claim that the suite was executed during the
migration or that Completion-specific acceptance tests exist.

## Intended functionality

The first goal is a small, production-shaped path from VS Code editor
observations to a Tertalis Completion application and back to the editor.
The eventual design needs to consider asynchronous requests, cancellation
of stale completions, shared model residency and coexistence with other
running Tertalis applications. These are **development objectives**, not
features available today.

The VS Code extension is responsible for editor-specific observations and
presentation. Shared runtime, provider and resource ownership remain
platform concerns. Application-specific policies and behavior belong to
the Completion workstream.

## Shared cross-repository coordination

This repository participates in the single Tertalis development
coordination system; the copied `ai-workflow/` tree here is not an active
independent inbox. Until the approved cross-repository backend cutover,
the authoritative file-based protocol, inbox and workstream state remain
on branch `actant-integration` in
[EnterTheNameHere/Turnix](https://github.com/EnterTheNameHere/Turnix/tree/actant-integration).

Read [AGENTS.md](AGENTS.md) before using coding agents or coordinating
implementation. A platform revision must be adopted through an
explicitly authorized and verified integration, not because newer
platform code is available elsewhere.

## Releases

There is no usable Completion release yet. The planned Tertalis
PackageManager, AppPack distribution and `tertalis` CLI are not currently
available Completion setup commands.
