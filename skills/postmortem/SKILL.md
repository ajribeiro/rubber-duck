---
name: postmortem
description: Turn the debugging conversation so far into a short "what I learned" note. Use when the user has just fixed a bug and asks for a postmortem, a summary of what went wrong, or runs /quack-debugger:postmortem.
---

# Duck postmortem

Write a five-line note about the bug the user just worked through in this conversation.

Use exactly these five lines:

```
Symptom: <what the user saw>
Cause: <what was actually wrong>
Clue: <the observation that cracked it>
Fix: <what changed>
Next time: <one habit or check that would have found it sooner>
```

- One sentence per line. Plain words.
- Only use facts from this conversation. If a line is unknown, write "unknown" rather than guessing.
- Do not add an introduction or a closing remark.
