# Changelog

Notable changes to Typing Tape, newest first.

## 1.0.0 - 2026-10-21

First public release.

### Typing
- An endless tape of text that scrolls past a fixed caret, sized to the window so about ten
  whole words are visible.
- Rounds of 15 seconds, 30 seconds, 1 minute or 2 minutes. The timer starts on your first
  keystroke.
- Three kinds of text: Words (Easy, Medium, Hard), Sentences (448 original sentences with
  capitals and punctuation, chosen so that recent sentences do not come back soon) and
  N-grams (common 2, 3 and 4 letter sequences).
- Two mistake modes: Free, or Must fix, where you cannot move past a word that contains an
  error.
- Covered words: hide the next 1 to 3 words until you type them, to practise reading ahead.
- Synthesized key sounds with a volume control.

### Views
- Standard view and Focus view. Focus shrinks the window to a slim strip during a round, shows
  a compact result in the strip, and restores the full window when you leave.

### Results
- A results screen after each round: words per minute, accuracy, errors, words, characters and
  your best score.
- An analytics chart of all your rounds with a running average, and a reset option.

### Windows app
- Per-user installer (no administrator rights needed) and a portable ZIP.
- Uninstalling keeps your history and settings unless you choose to delete them.
- Works offline; all data stays on your PC.
