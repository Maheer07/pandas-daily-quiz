# Daily agent instructions

You are running as a scheduled weekday task. Your job: generate today's 5-question NumPy/pandas quiz, review it, archive it, and email it. Follow these steps in order. Do not skip the review step or the archive commit even if you're confident the questions are good.

## 1. Orient yourself

- You are working inside a checkout of this repo. Run `git pull` to make sure you have the latest history first.
- Read `curriculum.md`, specifically the `Progress` section.
- Read the 3 most recent files in `questions/` (by filename/date — they're named `YYYY-MM-DD.md`), if any exist. If `questions/` is empty, this is Day 1 — start at roadmap topic 1.
- Determine today's date (UTC date is fine) and figure out `day_number` (`Progress.day_number + 1`) and which roadmap topic(s) today covers, per the rules written at the top of `curriculum.md`.

## 2. Write 5 questions

Format per question, multiple choice, 4 options (A-D), exactly one correct:

- Each question is a short pandas/numpy **code snippet or problem statement** — e.g. "given this DataFrame `df`, which line correctly does X" or "what does this code print" — not a bare definition question.
- Distractors must be **close/plausible**, not silly. Use real confusions: `.loc` vs `.iloc`, `axis=0` vs `axis=1`, `inplace=True` default assumptions, `merge` vs `join` vs `concat`, `apply` vs `map` vs `applymap`, off-by-one slicing, mutating vs returning a copy, etc.
- Question difficulty and topic should **build slightly on recent days** — reference or reuse a DataFrame/scenario from a recent question where it makes the "building on top of" connection concrete, don't just pick unrelated topics in isolation.
- Vary style day to day: some "which command", some "what's the output", some "spot the bug in this line".
- Tag each question with the roadmap topic number it covers.

## 3. Review before sending (do this yourself, don't skip it)

For each of the 5 questions, verify:

- Exactly one option is unambiguously correct given real pandas/NumPy semantics (mentally trace the code — don't guess).
- The 3 distractors are wrong for a clear, specific reason (not just "randomly different").
- The snippet is syntactically valid and would actually run.
- It isn't a near-duplicate of a question in the last 10 files in `questions/`.
- The explanation you'll put in the answer key is correct and says *why* the distractors are wrong, not just what the right answer is.

If a question fails review, rewrite it before moving on — don't send a question you're not confident about.

## 4. Archive it

Create `questions/YYYY-MM-DD.md` (today's date) with this structure:

```markdown
# Day <N> — <YYYY-MM-DD>

Topics: <roadmap topic name(s) and number(s)>

## Q1. <question text / code snippet>
A. ...
B. ...
C. ...
D. ...

## Q2. ...
(...Q3-Q5...)

## Answer key

1. **B** — <1-2 sentence explanation, including why the close distractors are wrong>
2. ...
```

Update `curriculum.md`:
- Bump `Progress.day_number`.
- Set `Progress.last_topic_index` to the topic index covered today (or the highest one, on a review day).
- Set `Progress.last_sent_date` to today's date.
- Set `Progress.last_topic` to a short label.
- Append one line to the `Log` section: `Day <N> — <date> — <topic label>`.

Commit both files together:

```
git add questions/<date>.md curriculum.md
git commit -m "Day <N>: <topic label>"
git pull --rebase
git push
```

If the push fails, retry once after `git pull --rebase`. If it still fails, still proceed to send the email (don't block the user's quiz on a git conflict) but say so plainly in your final summary.

## 5. Email it

Send via the Gmail tool to **mmaheer2001@gmail.com**.

- Subject: `Pandas/NumPy Daily Quiz — Day <N> — <YYYY-MM-DD>`
- Body:
  - One friendly opening line, no fluff, mention which topic(s) today builds on from previous days.
  - Q1-Q5 with their A-D options, plainly formatted, no answers yet.
  - A clear divider like `— — — don't scroll past here until you've answered — — —`
  - Then the answer key with explanations (same content as the archive file's answer key).
  - A closing line noting the day number and that past questions/answers live in the `pandas-daily-quiz` repo if they want to review or ask follow-ups later.
- Keep it plain text (or simple markdown-ish plain formatting) — no HTML needed, no attachments.

## 6. Final summary

After sending, state in your own final message: today's day number and topic(s), whether the git push succeeded, and whether the email send succeeded. If anything failed, say exactly what failed so it's visible in the run log.

## Notes

- This only runs on weekdays by schedule — you don't need to check the day of week yourself.
- Don't invent new roadmap topics on the fly except as `curriculum.md` itself describes (e.g. Cycle 3 planning after topic 40) — keep the progression coherent run over run since you have no memory except what's committed to this repo.
