# AGENTS.md

## Read this first

The full project brief lives in **`requirement.md`** at the repo root. Read it completely
before doing any work in this repo. It is the single source of truth and it already
contains everything, so you do not need to be told the task again.

- Project: **Vision-Guided Drone Food Delivery**, a business analysis for a Bangladesh
  (Dhaka focused) humanities group presentation.
- Group size: 8 presenters, 8 sections, one framework per section.
- `requirement.md` holds the topic, the presenter to section mapping, the required
  frameworks, the design and palette rules, the speech script rules, the media and
  animation rules, the prompt hand off format, the quality check, and the versioning and
  file naming conventions.

## Standing rules

1. Never write slides, a speech, or a deck generator without reading `requirement.md` in
   full first.
2. If a request is ambiguous, resolve it against `requirement.md` and state the resolution
   in one line before building. Only ask the user when two readings would produce
   materially different work.
3. Never touch the existing LLM Self Correction files in `output/` and `speeches/`. The
   drone deck is a new versioned artifact, named exactly as `requirement.md` section 5
   specifies.
4. Use the skills the brief names: `pptx` for the deck, `frontend-design` and
   `design-taste-frontend` for visual direction, `unslop` for all copy and the speech.
5. Run the quality check in `requirement.md` section 10 before reporting anything as done,
   and report the results rather than claiming success.
6. Keep writing rules from the brief even when they feel strict: no em dashes or en
   dashes, no raw URLs in the deck body, cite every figure, label unsourced numbers as
   Model assumption, and never invent a source.

## What to do when

- **"Make the deck", "build the slides", "start the presentation"**: follow
  `requirement.md` sections 3, 4, 5, 7, 8, then run section 10.
- **"Add animations / motion / video"**: follow section 8, and be honest that native
  PowerPoint animation timelines are not reliably writable with the current toolchain.
  Use motion inserts, frame based builds, or validated slide transitions instead.
- **"Give me the image and video prompts"**: follow the prompt hand off rules in section 8
  and write `media/asset_prompt_sheet.md`. Also paste the prompts into chat, the user
  wants to see them directly.
- **"Write the speech"**: follow section 9 and write `speeches/full_presentation_speech.md`
  with one labelled section per presenter.
- **"New version"**: bump to the next `-vN` suffix, never overwrite.

## Repo map

| Path | What it is |
|---|---|
| `requirement.md` | The project brief. Authoritative. |
| `output/` | Generated decks and PDFs. New drone deck goes here. |
| `speeches/` | Speech scripts. |
| `media/` | Image and video assets, prompt sheet, motion brief. Created when needed. |
| `.agents/skills/` | The pptx, frontend-design, taste and unslop skills. |

## Communication style

Be concise in chat. Report what was built, where, the quality check results, and the media
prompts. Do not narrate the brief back to the user, they wrote it.
