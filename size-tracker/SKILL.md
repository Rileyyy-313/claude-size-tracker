---
name: size-tracker
description: Keep a personal record of clothing and shoe sizes by brand, with fit notes, and answer "what size should I get?" before buying online. Use when the user says things like "Uniqlo M fits perfectly", "these Nikes are half a size small", "returned the Zara jacket, too tight in the shoulders", or asks which size to order from a brand.
---

# Size tracker

Sizing differs by brand and by cut. This keeps what actually fit you, so the next online order is right the first time.

## Where things live

`sizes.md` in the current folder. Create it on first use:

```markdown
# My sizes

## Measurements
(update with a date when they change)
- Height:
- Chest / bust:
- Waist:
- Hips:
- Inseam:
- Foot length:

## By brand

| Brand | Item / cut | Size | Fit | Notes | Date |
|---|---|---|---|---|---|

## Rules of thumb
(Claude adds patterns here once they show up, e.g. "Japanese brands: go one size up in tops")
```

Fit is one of: `perfect`, `small`, `large`, `returned`.

## What the user says → what to do

| User says | Do |
|---|---|
| "Brand X size M fits perfectly" | Add a row: Fit `perfect` |
| "… is a bit small / big" | Add a row: Fit `small` / `large`, and note where ("tight in shoulders", "long sleeves") |
| "Returned it" | Fit `returned`, with the reason if given |
| New measurements | Update Measurements with today's date; keep the old value in brackets: `Waist: 68 cm (2026-01-05; was 70)` |
| "What size for brand X?" | See below |

## Answering "what size?"

1. Same brand and similar cut on record: answer from it, citing the row ("You're an M in Uniqlo AIRism tees — perfect fit, Jan 2026").
2. Same brand, different cut: give the closest record and what's different.
3. New brand: compare the brand's size chart (if the user pastes it or it's on a page they're viewing) with Measurements. If neither is available, say there's no data and suggest checking the chart or reviews for "runs small / large".
4. If two records disagree, show both instead of picking one.
5. Add a pattern to "Rules of thumb" only after it shows up in 3+ rows, and tell the user when you do.

## Rules

- Record only what the user tells you. Never guess sizes or measurements.
- Measurements are private; don't copy them anywhere else.
- Keep replies to a line or two.
