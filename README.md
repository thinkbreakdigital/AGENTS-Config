# AGENTS Config

This repository stores the user-owned configuration for Codex and Claude. It does not include product-managed Codex system skills.

## Layout

- `codex/` contains files that install in `~/.codex/`.
- `claude/` contains files that install in `~/.claude/`.
- `shared/skills/` contains the editable source for skills used by both tools.
- `codex/skills/pixel-art-codex/` contains a Codex-only skill.

The `technical-writing` and `unslop` entries in both tool directories are relative symlinks to `shared/skills/`. Edit the shared copy. Do not edit a symlink target through a tool-specific directory.

`codex/solLead.md` applies only when GPT 5.6 Sol High is the active model.

## Install the configuration

Before you copy files, inspect the existing configuration directories. These commands replace files with the same names. They do not delete unrelated configuration or bundled skills.

```sh
mkdir -p ~/.codex/skills ~/.claude/skills

cp -a codex/AGENTS.md codex/FRONTEND.md codex/solLead.md ~/.codex/
cp -a codex/skills/pixel-art-codex ~/.codex/skills/
cp -a shared/skills/technical-writing shared/skills/unslop ~/.codex/skills/

cp -a claude/CLAUDE.md ~/.claude/
cp -a shared/skills/technical-writing shared/skills/unslop ~/.claude/skills/
```

Start a new Codex or Claude session after installation so it discovers the updated skills.

## Update a shared skill

1. Edit the skill in `shared/skills/`.
2. Review the change with `git diff`.
3. Copy that skill into both `~/.codex/skills/` and `~/.claude/skills/` using the matching `cp -a` command above.
4. Start new Codex and Claude sessions.

## Check the repository

Run these commands before a commit or push:

```sh
git status --short
find codex claude -type l -printf '%p -> %l\n'
```

The second command confirms that both tool directories still point at the shared skills.
