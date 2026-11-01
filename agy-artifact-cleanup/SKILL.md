---
name: agy-artifact-cleanup
description: Clean up temporary sprint artifacts, reference images, and scratchpad plans without touching conversation history or project code.
---

# Antigravity Artifact Cleanup Skill

Safely purge temporary planning documents, sprint scrap files, and feature-specific reference assets while preserving conversation transcripts, session state, and codebase integrity.

### Target Files for Removal

Locate and delete only temporary files created specifically for planning and scratch work during recent task iterations:

- **Temporary Plans & Trackers:** Files such as `implementation_plan.md`, `todo.md`, `task.md`, `scratchpad.md`, or temporary walkthroughs in the root or brain scratch directory.
- **Task Reference Images:** Temporary UI screenshots, mockups, or reference assets imported or saved specifically for feature prompting (e.g., inside `.brain/assets/`, temporary clipboard dumps, or temporary root asset folders).
- **Stale Diffs & Patches:** Temporary `.patch`, `.diff`, or scratch output dumps generated during intermediate debugging.

### Strict Safeguards (DO NOT DELETE)

Never remove or truncate:

- **Session & Brain Transcripts:** Any session logs, conversation memory, SQLite databases, indexers, or metadata files used by Antigravity to maintain chat context.
- **Project Assets & Source Code:** Any files tracked by git, actual production assets in `public/`, `assets/`, or `src/`, package configs, or permanent project documentation.
- **Unstaged Working Tree Code:** Never touch source code files edited during the sprint.

### Execution Procedure

1. Scan for the specific scrap files matching the targets above.
2. List the candidate files to delete and confirm they meet the safe criteria.
3. Remove the files.
4. Output a brief summary table of deleted files and freed space.
