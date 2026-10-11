# Size Tracker: a Claude skill

A Claude skill that keeps a personal record of what size fits you in each clothing and shoe brand, so you can ask "what size should I get?" before ordering online.

Sizing differs by brand and by cut. Tell Claude what fit and what didn't, in plain language, and it keeps a Markdown table by brand. Next time you shop, it answers from your own history.

## Example

```
You:    Uniqlo AIRism tee size M fits perfectly. Zara blazer size S was tight
        in the shoulders, returned it. Nike Pegasus 41 US 8 runs half a size small.
Claude: Saved all three.

You:    What size should I get for a Zara blazer?
Claude: You tried the Zara blazer in S and returned it, tight in the shoulders.
        Go with M.
```

The record lives in `sizes.md` in your working folder. See [`examples/sizes.md`](examples/sizes.md).

## What it does

- Records size, fit (`perfect`, `small`, `large`, `returned`) and notes per brand and cut
- Keeps your measurements, with history when they change
- Answers "what size for brand X?" from your records, citing which one
- Shows conflicting records instead of picking one
- Adds a "rule of thumb" only after a pattern shows up in 3+ records
- Never guesses sizes or measurements

## Install

Requires Claude with file access: the **Code** tab in the Claude desktop app, or Claude Code.

1. Copy the `size-tracker` folder into `~/.claude/skills/` (all projects) or `<your folder>/.claude/skills/` (one folder).
2. Start a new session in the folder where you want `sizes.md` to live.
3. Talk normally: "these Levi's 501 W28 fit perfectly".

## Customising

Everything is plain text in [`size-tracker/SKILL.md`](size-tracker/SKILL.md). Edit it, or ask Claude to change it.

## More

This skill comes from a personal Markdown system maintained by Claude. Other skills from it (meal logging, screenshot transcription, restock planning, order tracking) are at [sunburst54.gumroad.com](https://sunburst54.gumroad.com).

## License

MIT
