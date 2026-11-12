# Kryptaa changes by GPT

## Review only — user approval required

The user requires explicit permission before GPT changes project code, commits implementation changes, pushes implementation changes, or deploys. This branch contains only a review handoff requested by the user. Claude should review the setup and obtain the user's approval before applying changes or deploying. Do not merge this branch automatically.

## What GPT changed during the local Graphify setup

No application source code was changed by GPT during this setup. No application changes were committed, pushed, or deployed. This documentation commit is the subsequent, explicitly requested GitHub handoff.

Graphify 0.9.107 was installed in an isolated uv tool environment, and its bundled Codex skill was registered locally.

For the local Kryptaa website checkouts, mobile app, backend, worker, Higgsfield tooling and Sellbird project:

- Added `.graphifyignore` to exclude dependencies, build output, runtime data, and common secret files.
- Generated `graphify-out/` code indexes and cache/metadata files using `graphify update . --no-cluster`.
- Added a `Local Graphify context` section to `AGENTS.md`. The mobile app's existing Expo instruction was preserved.

For local reel and Kryptaa image folders:

- Added `ASSET_INDEX.md` filename inventories, without analyzing the media.
- Added a `Local media lookup` section to `AGENTS.md`.
- Added project-location lookup guidance in the relevant local Codex chat workspaces.

These additions remain local. They are not applied to application files on this branch. Generated graphs, caches, private project content, and local filesystem inventories are intentionally not uploaded here.

## Exact Graphify guidance added locally

```markdown
## Local Graphify context
For codebase questions, first query the existing local graph with `graphify query "specific symbols or topic" --budget 1500`. Read only relevant source files afterward. If the graph is stale, empty, or misses a symbol, use a targeted source search; the graph is not proof of correctness. Do not read the full graph JSON into model context.
After code changes, refresh with `graphify update . --no-cluster`. Keep extraction local and code-only; do not initiate semantic/media extraction or paid model calls just to maintain this index. Preserve existing user changes and project instructions.
```

The user's later permission restriction overrides the automatic refresh instruction above: GPT must not perform additional project writes without approval.

## Exact ignore patterns added locally

```gitignore
node_modules/
.venv/
.runtime/
.git/
dist/
build/
.expo/
.netlify/
.wrangler/
.playwright-mcp/
data/
.env*
.dev.vars*
sellbird.local.yaml
graphify-out/
*.min.js
```

## Validation and limitations

All seven local code graph builds completed, and a query against each graph returned nodes successfully. Indexing made no LLM/API calls. The 1500-token limit applies to graph query output, not total agent usage.

HTML/CSS layout, data-only JavaScript, documents, and media are not fully represented. Sellbird SQL extraction was skipped because its optional SQL parser was not installed. These indexes reflect local checkouts, not necessarily GitHub HEAD or deployed code. No 80% saving was measured. Image/video generation costs and pinned ChatGPT conversations are unaffected.

## Claude review checklist

1. Decide whether to retain local-only Graphify guidance and generated indexes.
2. Review ignore patterns and coverage before relying on the graph.
3. If cleanup is approved, remove only these setup additions and only the appended GPT sections in existing instruction files. Preserve the app's Expo instruction.
4. Existing app and worker source changes were not made by GPT in this setup; do not reset, overwrite, stage, or deploy them as part of cleanup.
5. No application deployment is needed for Graphify. Do not push or deploy application changes without the user's authorization.
