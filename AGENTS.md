# AGENTS.md

## Read this first

The full project brief lives in **`requirement.md`** at the repo root. Read it completely
before doing any work in this repo. It is the single source of truth and it already
contains everything, so you do not need to be told the task again.

- Project: **AeroSetu**, a vision and AI powered drone delivery business analysis for a
  Bangladesh humanities group presentation. Food delivery is the first market, not the only one.
- 37 slides, 8 presenters, **8 sections**, 8 frameworks. One section per presenter. There are
  no section divider pages.
- `requirement.md` holds the name and branding rules, the Vision to Jev to GLM escalation
  requirement, the Rajshahi-first geography argument, the eleven section and presenter mapping,
  the palette and font sizes, the header, footer and slide numbering rules, the real photograph
  sourcing rules, the motion approach, the speech rules, the quality check, and the versioning and
  file naming conventions.

## Standing rules

1. Never write slides, a speech, or a deck generator without reading `requirement.md` in
   full first.
2. If a request is ambiguous, resolve it against `requirement.md` and state the resolution
   in one line before building. Only ask the user when two readings would produce
   materially different work.
3. Never touch the existing LLM Self Correction files in `output/` and `speeches/`. The
   drone deck is a new versioned artifact, named exactly as `requirement.md` section 10
   specifies.
4. Use the skills the brief names: `pptx` for the deck, `frontend-design` and
   `design-taste-frontend` for visual direction, `unslop` for all copy and the speech.
5. Run the quality check in `requirement.md` section 13 before reporting anything as done,
   and report the results rather than claiming success.
6. Three non negotiable design rules, because they have been corrected before: **white
   background only, no dark slides at all**, **12 pt absolute font floor with no exceptions**,
   and **real licensed photographs rather than AI generated imagery**.

## What to do when

- **"Make the deck", "build the slides"**: follow `requirement.md` sections 4, 5, 6, 7, 9, 10,
  then run section 13.
- **"Add animations / motion / video"**: follow section 12, and be honest that native
  PowerPoint animation timelines are not reliably writable with the current toolchain.
- **"Give me the image and video prompts"**: prompts are the fallback for anything the
  Wikimedia Commons photograph route could not cover. Real photographs remain primary.
- **"Write the speech"**: follow section 12 and write `speeches/full_presentation_speech.md`
  with one labelled section per presenter.
- **"New version"**: bump to the next `-vN` suffix, never overwrite. Never recreate the deleted
  `Drone_Food_Delivery_*` drafts.

## Repo map

| Path | What it is |
|---|---|
| `requirement.md` | The project brief. Authoritative. |
| `build/` | Deck generator source. `generate.js` is the entry point and refuses to build if copy will overflow its box. `slidenum.py` swaps the static counter for a live PowerPoint field after every build. `qa_layout.py` checks a rendered PDF for overflow, collision, undersized text and out of bounds text. `make_motion.py` builds the MP4s. |
| `output/` | Generated decks. New SkyBhat deck goes here. |
| `speeches/` | Speech scripts. |
| `media/img/` | Nine real photographs, the client supplied `slide_one_hero.png`, and `credits.json` with licences and authors. |
| `build/v1.pdf` | Rendered PDF of the current deck, used for visual QA. Regenerate, do not commit stale. |
| `media/motion/` | Generated MP4 motion assets and poster frames. |
| `.agents/skills/` | The pptx, frontend-design, taste and unslop skills. |

## Local tooling notes

- No LibreOffice and no `pdftoppm` on this machine. Render for visual QA by exporting the
  deck to PDF through Microsoft PowerPoint over AppleScript (`save ... as save as PDF`,
  passing the output path as an HFS path string) then rasterising with `pymupdf`.
- `ffmpeg` and `ffprobe` are available for the motion assets.
- Build order: `node build/generate.js` then `python3 build/slidenum.py <pptx>`. The second step is
  not optional, otherwise the page numbers are static text.
- The build fails on estimated text overflow. If it stops, either shorten the copy or grow the box.
  Do not raise the font floor or shrink the box to get past it.
- `build/qa_layout.py` cannot see text that overflows its own card without hitting another block,
  so the build time estimator in `build/design.js` is the real guard. Run both.
- Wikimedia Commons images: query `commons.wikimedia.org/w/api.php` for
  `imageinfo` + `extmetadata`, throttle to roughly one request every three seconds or you
  will hit HTTP 429.
- **Quit PowerPoint before rendering.** A stale `~$` lock file from a previous export makes
  PowerPoint write "The picture can't be displayed" and silently emit a short PDF. Check with
  `ls output/ | grep '~\$'`, remove the lock, and quit the app.
- `slide_one_hero.png` is client supplied, not a Wikimedia photograph, so it carries no licence
  line in `credits.json` and no credit caption on the slide.

## Communication style

Be concise in chat. Report what was built, where, the quality check results, and the media
prompts. Do not narrate the brief back to the user, they wrote it.
