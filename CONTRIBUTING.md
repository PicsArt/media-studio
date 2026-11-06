# Contributing

Thanks for helping with Picsart Media Studio for Claude. Please read this before you open an issue or a pull request.

## Repository structure

| Path | What it is |
|---|---|
| `skills/` | One folder per skill, named in kebab-case |
| `.claude-plugin/` | The plugin manifest (`plugin.json`) and the marketplace for Claude Code (`marketplace.json`) |
| `.mcp.json` | The one MCP server the plugin connects: the Picsart Media Studio connector |
| `generated.json` | The skill folders that are generated; see [Generated skills](#generated-skills) |
| `scripts/` | The skill compliance checker and the security scanner |
| `.github/workflows/` | CI: both checks run on every pull request |

## Skills use Media Studio's tools only

Every tool a skill names must be a tool the Picsart Media Studio connector serves. A skill must not
send Claude to another server or tool, and it must not generate or alter media with AI. Keep
`.mcp.json` to `type` and `url`: the connector handles sign-in itself.

## Generated skills

The folders listed in [`generated.json`](./generated.json) are generated, and the next generation
overwrites them. Don't edit them in a pull request; open an issue that describes the change instead.
A hand-written skill must not reuse a generated folder's name.

## Compliance rules

Every skill must pass `python3 scripts/check-skill-compliance.py` before merge. It checks the open
[Agent Skills specification](https://agentskills.io/specification) and Anthropic's
[skill-authoring rules](https://platform.claude.com/docs/en/agents-and-tools/agent-skills/best-practices).

```bash
python3 scripts/check-skill-compliance.py               # all skills
python3 scripts/check-skill-compliance.py skills/foo    # one skill
python3 -m unittest discover -s scripts -p 'test_*.py'  # the checker's own tests
```

`.github/workflows/skill-compliance.yml` runs the same check on every pull request and blocks the
merge when it fails. `.github/workflows/scan-skills.yml` scans changed skills for unsafe instructions.

## Issues

Check the [existing issues](../../issues) first. For a bug, name the skill and the plugin version,
what you expected and what happened, and the request you gave Claude.

## Pull requests

1. Branch from `main`: `feat/` for a new skill, `fix/` for a correction, `chore/` for maintenance.
2. Run the compliance check and the checker's tests.
3. Open the pull request with what changed, why, and how you tested it in Claude.

The Picsart team reviews and merges.

## Versions

`version` in `.claude-plugin/plugin.json` follows [Semantic Versioning](https://semver.org/) and rises
with every release: Claude reads each new version from this repository.

## License

By contributing, you agree that your contribution is provided under the [MIT License](./LICENSE).
