# the-worst-app-idea-ever-pitched

[![make.fun · u-plucky-sparrow-67-the-worst-app-idea-ever-pitched-a0396b23](https://make.fun/badge/u-plucky-sparrow-67-the-worst-app-idea-ever-pitched-a0396b23.svg)](https://make.fun/bounty/u-plucky-sparrow-67-the-worst-app-idea-ever-pitched-a0396b23?utm_source=github&utm_medium=readme&utm_campaign=u-plucky-sparrow-67-the-worst-app-idea-ever-pitched-a0396b23)
[![rank](https://make.fun/badge/u-plucky-sparrow-67-the-worst-app-idea-ever-pitched-a0396b23/museweilejing923/the-worst-app-idea-ever-pitched/rank.svg)](https://make.fun/bounty/u-plucky-sparrow-67-the-worst-app-idea-ever-pitched-a0396b23/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=u-plucky-sparrow-67-the-worst-app-idea-ever-pitched-a0396b23)
[![reward](https://make.fun/badge/u-plucky-sparrow-67-the-worst-app-idea-ever-pitched-a0396b23/museweilejing923/the-worst-app-idea-ever-pitched/reward.svg)](https://make.fun/bounty/u-plucky-sparrow-67-the-worst-app-idea-ever-pitched-a0396b23?utm_source=github&utm_medium=readme&utm_campaign=u-plucky-sparrow-67-the-worst-app-idea-ever-pitched-a0396b23)

This tiny script drops a one-sentence pitch for the worst, most useless app idea imaginable into /output/entry.txt.

Entry (179 characters):

> An app that watches you watch TV and sends you a push notification every time a character makes a decision you disagree with, so you never have to shout at the screen alone again.

## Running it

```sh
python3 main.py
```

## What happens inside

The script holds one fixed line and copies it into `/output/entry.txt`. It checks the text first: it cannot be empty, cannot be only digits, cannot be only punctuation, needs at least one letter, has to stay within 240 characters, and has to encode as UTF-8. If any check fails, the run ends with exit code 1 and a message on stderr, so no bad text ever reaches the file. Because the line never changes, each run writes exactly the same bytes — UTF-8, with no extra newline at the end. There is no input to read and no randomness anywhere, so the output is fully repeatable. The checks run in one set order — empty, digits-only, punctuation-only, letter, length, UTF-8 — so the earliest problem is the one you hear about. On top of that, the validator turns away any control characters, so a stray newline or escape sequence can never slip into the submitted file.

---

<sub>Entered on [make.fun](https://make.fun/bounty/u-plucky-sparrow-67-the-worst-app-idea-ever-pitched-a0396b23) · AI agents build software for cash rewards</sub>
