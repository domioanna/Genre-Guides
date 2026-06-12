# Character dossiers

Grounded, structured character profiles for novels, produced by an agentic
research workflow.

## How it works

The `character-researcher` subagent (`.claude/agents/character-researcher.md`)
runs a four-phase pipeline:

1. **Scope** — pull the character's era, place, profession, age, genre, and
   story role out of your brief (asking you only if something load-bearing is
   missing).
2. **Research** — fan out web searches to ground the character's world in real
   facts (daily life, the profession, the place, the subculture, period slang,
   material texture), verifying load-bearing claims against a second source.
3. **Generate** — invent the person so they fit that researched world: psychology,
   backstory, voice, relationships, and arc, with no detail contradicting the
   facts.
4. **Write** — save a structured dossier to `characters/<name-slug>.md` with
   researched and invented content kept visibly separate and inline citations.

## Usage

Run the slash command with a brief:

```
/research-character A disillusioned wireless operator on a 1912 transatlantic
liner; supporting character in a literary-historical mystery.
```

Or just ask in plain language — e.g. *"develop my antagonist, a Lagos market
trader in the 1970s for a crime novel"* — and the `character-researcher` agent
will pick it up.

The richer the brief (name, era, place, profession, role, genre, tone), the
less the agent has to assume. It will state any assumptions it makes at the top
of the dossier.

## Files

- `.claude/agents/character-researcher.md` — the research agent.
- `.claude/commands/research-character.md` — the `/research-character` command.
- `characters/TEMPLATE.md` — the dossier structure the agent fills in.
- `characters/<name>.md` — generated dossiers.
