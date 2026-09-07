# pandas-daily-quiz

Archive for the daily NumPy/pandas quiz emails.

- `curriculum.md` — the topic roadmap and progress tracker. The daily cloud agent reads this to decide what today's questions should build on.
- `questions/YYYY-MM-DD.md` — one file per weekday: the 5 questions sent that day, their options, and an answer key with explanations. This is the persistent "memory" — any Claude Code session (or the daily agent itself) can read these files to answer follow-up questions like "what was the answer to day 12, question 3?".
- `PROMPT.md` — the exact instructions the scheduled cloud agent follows each run. Edit this file to change how questions are generated, reviewed, or emailed — the routine itself just points here, so no need to touch the routine config for behavior changes.

This repo is written to by a scheduled Claude Code cloud routine, weekdays at 10:00 Europe/London.
