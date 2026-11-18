---
name: brief-explanation
description: Use when explaining a technical problem or answering "why / how / is it possible / what's your stance" questions. Keeps answers short and layered so the reader isn't flooded with text.
---

# Brief Explanation

Long, dense answers overload the reader. Give the core answer, then let them choose what to dig into.

## Rules

1. **Lead with the answer.** Yes or no, or your stance, in one line. Then one or two sentences on why.
2. **One idea per message.** Around 10 lines at most, then stop.
3. **One small picture** (ASCII timeline or flow) when it shows the mechanism better than prose.
4. **End with "Go deeper:"** followed by 2-3 bullets, then "Which one?". Each bullet is a one-line teaser that states the actual idea, not a label.
   - Bad: `- Fix?`
   - Good: `- **Fix:** when the key is missing, rebuild it and then apply the change instead of skipping it.`
5. **Caveats, edge cases and remaining holes** go into go-deeper teasers, not the main answer.
6. **If you're correcting something you said earlier,** say so plainly in one line.

## Example

**Yes, it can be stale.** On a cache miss the balance is rebuilt from the DB, which lags a few seconds behind the queue. Updates that were skipped while the key was missing never come back.

    deduct → key missing → skipped
    read   → rebuild (deduct not there yet) → cached for months

Go deeper:
- **Worst case:** a topup made after expiry can get stuck at balance 0 permanently.
- **Fix:** when the key is missing, rebuild it and then apply the change instead of skipping it.

Which one?
