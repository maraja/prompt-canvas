# Prompt Canvas

A free, single-page board for building the prompt you actually meant to write.

Lay out cards for your goal, who you are, how you work, examples, templates, constraints and the output you want. Drop or paste screenshots, videos and documents, connect them to the cards they belong to, and export one zip: `PROMPT.md` plus an `assets/` folder holding every file the prompt mentions. Drag it into Claude Code, ChatGPT or any other assistant.

- Cards compile in section order, then by position on the board
- Files connected to a card are written inside that card's part of the prompt
- `{{blanks}}` are filled in at export, so one board works as a reusable template
- Coverage meter shows which sections are missing; Compare puts two boards side by side
- Markdown editor, undo/redo, light and dark themes

Everything stays in your browser (IndexedDB). Nothing is uploaded anywhere.

## Run locally

It's one static file with no build step:

```bash
python3 -m http.server 4321
```

Then open http://localhost:4321.
