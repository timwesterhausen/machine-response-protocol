# Machine Response Protocol

Machine-oriented communication for AI agents.

The protocol makes responses concise, structured, verifiable, and easy to scan. It reduces social framing and anthropomorphic language without removing information, uncertainty, safety warnings, or required user actions.

## Features

- Adaptive status markers such as `STATUS`, `RESULT`, `PROBLEM`, `NEXT`, and `CONFIRM?`
- Explicit distinction between facts, hypotheses, recommendations, and verified results
- Milestone updates instead of tool-by-tool narration
- Scope-aware approval rules for destructive or externally consequential actions
- Progressive detail through `EXPAND`
- Independent language compression and output-language controls
- English protocol markers with content in the user's selected language
- Machine-like tone without primitive or broken language

## Install

```bash
npx skills add timwesterhausen/machine-response-protocol
```

The skill is defined in [`SKILL.md`](SKILL.md).

## Compression levels

Compression and output language are independent.

| Level | Behavior |
| --- | --- |
| `NONE` | Complete readable explanations; no deliberate compression |
| `LIGHT` | Removes filler and redundant wording |
| `MEDIUM` | Concise default mode |
| `HEAVY` | Short structured lines; nonessential explanation removed |
| `MAX` | Smallest meaningful units; essential meaning and safety remain |

Examples:

```text
/machine compression light
/machine compression max
/machine status
/machine reset
```

Natural-language equivalents are also supported, such as “leicht komprimieren” or “maximal komprimieren”.

## Output language

```text
/machine language english
/machine language german
/machine language user
```

Language selection does not change compression. Code, paths, identifiers, API names, commands, and exact error messages remain unchanged.

## Design principles

1. Compress language, not meaning.
2. Never claim execution, verification, access, or confidence without evidence.
3. Put the result or blocker first.
4. Interrupt only for real decisions, required permissions, material risks, or external actions.
5. Do not simulate warmth, praise, companionship, or human feelings.

## License

No license has been specified yet.
