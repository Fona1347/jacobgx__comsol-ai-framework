# AGENTS.md - Codex Instructions for AICOMSOl

This repository is a COMSOL Multiphysics modeling knowledge base and workflow guide for AI coding agents.

## Primary Rule Source

Use `CLAUDE.md` as the full modeling rulebook unless this `AGENTS.md` gives a Codex-specific override.

For Codex work, treat the rules in `CLAUDE.md` as mandatory project instructions:

- Search `database/` before writing COMSOL API code.
- Verify API syntax against `database/api_reference/`.
- Use `database/applications/` as the primary source for official Java examples.
- Use `database/experience/` for debugging and convergence diagnosis.
- Build complex models incrementally instead of writing all physics at once.
- For tasks scoped to this repository, put generated model files, scripts, and
  outputs under `result/<project>/`.
- For Huayun local runtime projects under `jacobgx_base`, follow that
  workspace's closer `AGENTS.md` and keep project files under
  `E:\hycodespace\simulation\jacobgx_base\projects\<project_id>`.

## Codex-Specific Workflow

Before implementing a COMSOL modeling task:

1. Read this file and `CLAUDE.md`.
2. Search the knowledge base for similar models and API patterns.
3. State the selected modeling route:
   - Java batch for new models.
   - MPh/Python for existing `.mph` model inspection, parameter edits, debugging, or parameter sweeps.
   - `comsolbatch -pname/-plist` for simple parameter overrides.
4. For complex or coupled models, present the geometry, physics, boundary conditions, study type, and validation plan before writing the full model.

## COMSOL Runtime

Use the `COMSOL_INSTALL_DIR` environment variable as the COMSOL Multiphysics root.

Expected subpaths:

- `java/win64/jre/bin/javac.exe`
- `plugins/`
- `bin/win64/comsolbatch.exe`

Do not hard-code a local COMSOL installation path into reusable project files unless the user explicitly asks for a machine-local script.

## Editing Discipline

- Do not modify official reference data under `database/` unless the task is explicitly to maintain the knowledge base.
- Do not place personal sync scripts or one-off machine setup files inside the repository.
- Preserve `CLAUDE.md` for Claude Code compatibility; `AGENTS.md` is the Codex entrypoint.
