# Local Setup - Huayun COMSOL Workspace

This file documents how this local fork of AICOMSOl is used on the
`E:\hycodespace` workstation. It is local operating guidance, not an upstream
installation requirement.

## Repository Role

AICOMSOl is used as the COMSOL knowledge base and AI modeling rulebook:

- `AGENTS.md` is the Codex entrypoint.
- `CLAUDE.md` remains the full modeling rule source.
- `database/` provides API references, official Java examples, model cards, and
  debugging experience.

Do not use this repository as the main simulation output workspace. Generated
models, figures, logs, and project-specific code should live in
`jacobgx_base`.

## Local COMSOL Runtime

The local COMSOL Multiphysics root is:

```text
D:\Softwares_02\COMSOL64\Multiphysics
```

For reusable scripts, prefer the `COMSOL_INSTALL_DIR` environment variable
instead of hard-coding this path.

Expected runtime tools:

```text
%COMSOL_INSTALL_DIR%\java\win64\jre\bin\javac.exe
%COMSOL_INSTALL_DIR%\bin\win64\comsolbatch.exe
%COMSOL_INSTALL_DIR%\bin\win64\comsolmphserver.exe
%COMSOL_INSTALL_DIR%\plugins
```

## Runtime Workspace

The local COMSOL/AI runtime database is:

```text
E:\hycodespace\simulation\jacobgx_base
```

Use that workspace for:

- shared PowerShell helpers;
- local conda/MPh environments;
- optional MCP startup snippets;
- concrete simulation projects;
- build artifacts, `.mph` files, figures, logs, and comparison outputs.

New simulation or reproduction projects should be created under:

```text
E:\hycodespace\simulation\jacobgx_base\projects\<project_id>
```

## Automation Routes

Use the shared helpers in `jacobgx_base\scripts`:

```text
compile-java-api.ps1        Java API compilation
run-java-batch.ps1          COMSOL batch execution
mph-python.ps1              MPh Python entrypoint
start-wjc-comsol-mcp.ps1    backend COMSOL MCP route
start-gui-comsol-mcp.ps1    GUI Java Shell MCP route
comsol-env.ps1              local COMSOL runtime variables
```

Route selection:

- New COMSOL model construction: Java API batch.
- Existing `.mph` inspection, parameter edits, debugging, or sweeps: MPh.
- Simple parameter override on existing models: `comsolbatch -pname/-plist`.
- Visible COMSOL Desktop interaction: GUI Java Shell MCP, only after manually
  opening COMSOL Desktop and Java Shell.

## Sync Script

The fork synchronization script is intentionally stored outside this repository:

```text
E:\hycodespace\Forks\jacobgx\sync-AICOMSOl.ps1
```

Keeping it outside the repository avoids committing machine-local maintenance
scripts to the fork.

## Agent Usage

When working in this repository, Codex should read `AGENTS.md`, then
`CLAUDE.md`, then search `database/` before writing COMSOL API code.

When working in `jacobgx_base` or a project below it, Codex should use
`jacobgx_base\AGENTS.md` as the local bridge back to this repository.
