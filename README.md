# no-ai-slop

A Claude Code skill that edits drafts into sharper, more human writing and removes 20+ AI writing patterns. This is a fork of [Peter Yang's no-ai-slop](https://github.com/petergyang/no-ai-slop) tuned for people who write punchy product and exec communications, plus a voice file so the skill edits toward your voice instead of a generic one.

## What's different from the original

**A smaller banned list.** The original bans 26 words outright. This fork bans 6 (cutting-edge, paradigm shift, game changer, this is huge, this changes everything, beacon) and moves the rest (leverage, streamline, robust, and friends) to a watch list. In product and business writing those are normal working vocabulary. The skill cuts them when they decorate and keeps them when they are the precise term.

**Punchy moves are allowed in moderation.** The original treats colon punch lines, sentence fragments, mid-sentence bold, and "not X, it's Y" contrasts as slop everywhere. This fork allows each one when it is doing real work: an occasional colon-led punch line, a deliberate fragment, bold on the single number that matters, one contrast that corrects a belief the reader actually holds. Stacking any of them still gets cut.

**One new pattern.** Compressed verdicts: a judgment folded into a clever label, like "your trace-id instinct is the expensive way to close it." The skill unpacks these into a plain claim plus its tradeoff.

**A voice file.** `skills/no-ai-slop/voice.md` describes how you sound, the formats you write in, and your house conventions. The skill reads it before editing, and it wins whenever it conflicts with the general rules. The shipped file is a worked example from a product manager's voice; replace it with your own.

Everything else is Peter's skill, including his newer additions (the portability test, show-don't-tell, and the interpretive metadiscourse pattern).

## Install

Copy the skill folder into your Claude Code skills directory:

```bash
git clone https://github.com/charleschen-yhoo/no-ai-slop.git
cp -r no-ai-slop/skills/no-ai-slop ~/.claude/skills/
```

Then edit `~/.claude/skills/no-ai-slop/voice.md` to describe your own voice (or delete it to use the general rules only).

## Use

In Claude Code:

```
/no-ai-slop <paste your draft>
```

Two modes:

- **Edit (default).** Returns the edited draft plus a What changed section. Makes the minimum effective edit and preserves your voice.
- **Detect.** Ask it to audit or flag a draft without rewriting. It names each slop pattern found, quotes the line, and gives the fix.

## Credits

Original skill by [Peter Yang](https://github.com/petergyang/no-ai-slop), MIT licensed. Modifications by Charles Chen, also MIT.
