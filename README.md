# rubber-duck

Rubber duck debugging for Claude. The duck helps you find the bug yourself: it asks questions and never gives the answer.

## What's in it

| Piece | What it does | Where it works |
| --- | --- | --- |
| `duck` skill | Talks you through a problem using questions only | Anywhere skills work |
| `postmortem` skill | Turns the conversation into a five-line "what I learned" note | Anywhere skills work |
| `duck-reviewer` agent | Reviews a change and replies only with questions | Apps that support plugin sub-agents |
| Quack hook | After a shell command fails, prints "Quack." and one debugging prompt | Claude Code only |

The hook and its script need a local shell, so they do nothing outside Claude Code. The two skills do not depend on them.

## Install

From a marketplace that lists it:

```
/plugin install rubber-duck@<marketplace>
```

Or try it locally without installing:

```
claude --plugin-dir ./rubber-duck
```

## Use

```
/rubber-duck:duck
/rubber-duck:postmortem
```

Ask for the reviewer by name: "have the duck-reviewer look at my diff".

## Permissions

- The `duck` skill pre-approves read-only tools for itself: `Read`, `Grep`, `Glob`, `git diff` and `git log`. It never edits files.
- The `duck-reviewer` agent cannot use `Write` or `Edit`.
- The hook runs `bin/quack`, a short bash script that prints one line. It reads no input, writes no files, and makes no network calls.

## Privacy

The plugin has no server, collects nothing, and sends nothing anywhere.

## Changelog

- 0.1.0: first release.

## License

MIT
