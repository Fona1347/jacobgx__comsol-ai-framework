# Local Changelog

This changelog records Huayun-local fork changes relative to
`jacobgx/AICOMSOl`. It is separate from upstream release history.

## 2026-07-02

- Documented the local COMSOL 6.4 runtime path and the split between this
  AICOMSOl fork and `E:\hycodespace\simulation\jacobgx_base` in
  `LOCAL_SETUP.md`.
- Documented that concrete simulation projects, build artifacts, `.mph` files,
  figures, logs, and comparison outputs belong under `jacobgx_base`, not inside
  this knowledge-base repository.
- Recorded the repo-external fork synchronization script location:
  `E:\hycodespace\Forks\jacobgx\sync-AICOMSOl.ps1`.
- Added this local changelog for fork maintenance tracking.

## 2026-07-01

- Added `AGENTS.md` as the Codex project entrypoint.
- Kept `CLAUDE.md` as the complete modeling rule source for Claude Code
  compatibility and upstream structure preservation.
- Updated `README.md` so the project describes both Codex and Claude Code
  workflows.
- Clarified that Codex reads `AGENTS.md`, while the full modeling rules remain
  in `CLAUDE.md`.
