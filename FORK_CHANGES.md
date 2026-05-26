# Fork Changes

This is a fork of [alfredang/notebooklm-mcp](https://github.com/alfredang/notebooklm-mcp).

## Sync status

**In sync with upstream.** All changes made in this fork have been contributed back to
`alfredang/notebooklm-mcp` and merged. The fork tracks upstream `main` directly.

## History of contributions

This fork was the primary development environment during May 2026. The following
changes originated here and were pushed upstream:

| Commit | Description |
|--------|-------------|
| `4107c55` | Initial commit: NotebookLM Assistant skill for Claude Code |
| `0b39686` | Implement premium NotebookLM MCP server with full artifact generation (podcasts, videos, slides, mind maps, quizzes, flashcards, reports) |
| `8c1ed28` | Comprehensive README with step-by-step installation guide |
| `29f5f42` | Fix: use full path to `uv` for Claude Desktop compatibility |
| `04cc2b6` | Docs: make README platform-agnostic for macOS and Windows |
| `777893c` | Docs: simplify config file instructions |
| `988b61c` | Docs: clarify notebooklm-py dependency installation |
| `ff6e970` | Docs: update folder name to `notebooklm-mcp` throughout README |
| `860a652` | Docs: update title to NotebookLM MCP |

## Usage in h2-stack

This submodule provides the NotebookLM MCP server deployed as `h2-notebooklm` on
Azure Container Apps. The server wraps `notebooklm-py` (Google NotebookLM browser
automation) via FastMCP, adding:

- Azure Files cookie persistence (`/auth-store` SMB mount)
- Admin upload UI for refreshing cookies
- `H2_BEARER_TOKEN` auth middleware
- Health endpoint compatible with h2-stack `/api/status` aggregator

To check for upstream updates:
```bash
git fetch upstream
git log HEAD..upstream/main --oneline
```
