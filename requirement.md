# Presentation Requirements: AeroSetu

## 1. Project summary

Keep this block short enough to memorise. It is the whole project in a few lines.

AeroSetu is a **vision-first autonomous delivery system** for Bangladesh. The name is
deliberately sector neutral: food delivery is the first market, and the same corridor, pad and
model stack is intended to carry medical, pharmaceutical, e-commerce and document delivery
afterwards. Any sentence that implies food is the only possible market is wrong.

The first implementation is a **vision-first autonomous delivery system** for Bangladesh food delivery. Computer
vision handles navigation, obstacle detection, corridor following and safe balcony landing
continuously and on board the aircraft. When the network is unavailable or unstable, the drone
falls back to **vision-only local autonomy** and predefined safe behaviours.

In normal operation vision remains the main system, while **Jev** is invoked only when a fast,
bounded decision is required. Jev evaluates structured flight and environment state and selects
an action: continue, reposition, abort landing, or return home. For difficult, ambiguous or
unusual situations **GLM-5.3-Flash** acts as the higher level multimodal reasoning model.

The model choice follows an **AI escalation approach: Vision, then Jev, then GLM when
necessary**, instead of running an expensive reasoning model on every flight. GLM-5.3-Flash was
chosen because we expect its stronger intelligence and lower cost per completed task to beat
using a larger reasoning model for every case.

Hard safety rules, state estimation, path planning and flight control stay local and
deterministic. The drone can always fly safely with no AI and no network.

**Footprint:** the pilot starts in **Rajshahi**, a fourth scale Bangladeshi city, and scales to
**Dhaka** once permission and unit economics are proven.

## 2. Purpose of this file

This file is the single source of truth for the deck. Read it in full before generating anything.

The deck is a **humanities (business and management) course presentation**, judged on business
reasoning. Every section uses a named framework and makes an argument.

**Framing rule:** it must read as a plan a real team could execute in Bangladesh, not a concept
piece. Every claim ties to a named regulator, a named precedent, a real price, or a labelled
Model assumption.

## 3. Name and branding

- Use **AeroSetu** everywhere.
- Standing descriptor, printed in the footer of every slide: **Vision and AI powered drone food
  delivery**. It is the only line that goes in the footer, and it never changes per section.
- "SkyBhat" must not appear anywhere.
- "As the crow flies.", "HUMANITIES GROUP PRESENTATION", "8 presenters | 8 frameworks | 47 slides"
  and similar decorative filler are banned. No eye brow strapline on the title slide. Counts of
  slides, frameworks or presenters never appear on a slide.
- Trademark and domain availability has **not** been checked. Say so if asked.

## 4. Technology: vision, Jev and GLM

Three tiers, and all three must appear in the deck.

| Tier | Runs where | Job | Trigger |
|---|---|---|---|
| Vision | On the aircraft, always | Navigation, obstacle detection, corridor following, balcony landing, pad occupancy | Continuous |
| Jev | Hub, on demand | Scores structured flight and environment state, returns a typed action with calibrated confidence: continue, reposition, abort landing, return home | Only when a fast bounded decision is needed |
| GLM-5.3-Flash | Hub, on demand | Higher level multimodal reasoning for difficult, ambiguous or unusual situations | Rare escalation only |

**Always local and deterministic:** hard safety rules, state estimation, path planning, flight
control. The safety path never touches a network. If the link drops, the aircraft flies
vision-only and lands.

### Verified model facts, citable

- **GLM-5.3-Flash**, Z.ai / Zhipu AI, released 26 Aug 2026. 320B total parameters, 18B active,
  mixture of experts, first natively multimodal model in the GLM-5 series. 1M token context,
  131,072 max output. MIT licence, weights ungated on Hugging Face, commercial use permitted.
  Exposes a `reasoning_effort` parameter with low, high and max. Artificial Analysis Intelligence
  Index 57, against a median of about 27 for open weight models of a similar size.
- **Jev**, TypeSafe AI, early access 15 Sept 2026. A "System One" structured decision model, not a
  text generator. Returns typed values with calibrated probabilities. Its own documentation
  states it cannot replace an LLM.
- **Jev is proprietary and hosted, with no public weights.** This is stated as a real dependency
  risk, not hidden. Projects that resemble open Jev are not Jev, and at least one of them is
  distributed under a **non-commercial** licence, so it cannot run a business.

## 5. Geography: Rajshahi first, then Dhaka

Citable facts to use for Rajshahi:

- Fourth largest city in Bangladesh. Population 553,288 at the 2022 census; the wider
  agglomeration with Nowhata and Katakhali is about 1 million. Area 121 sq km.
- Urbanisation rate 32.93 percent, and urban growth of roughly 8 percent a year.
- Ranked the most polluted city in Bangladesh by IQAir on 16 March 2025, with an AQI of 162
  against Dhaka's 134 on the same day.
- Four flyover and overpass projects worth about Tk 490 crore began in December 2023 and were
  still unfinished in September 2026, with residents reporting worse congestion.
- Traffic is 63 percent commercial vehicles. Auto rickshaw, rickshaw and motorcycle together
  are about half of all vehicular traffic. Motorised traffic is growing about 8.5 percent a year.
- Known as the "Education City", home to Rajshahi University and RUET.

The honest argument for Rajshahi first: a smaller bet on an unsolved regulator, lower fixed
costs, and a city whose roads are visibly failing to keep up with demand.

The honest weakness, to be stated on the slide: Rajshahi is less dense than Dhaka, so corridors
are longer relative to our 6 km range and we need a higher density of pad sites per corridor.

## 6. Team, sections and framework assignment

| # | Student ID | Presenter | Section | Framework |
|---|---|---|---|---|
| 1 | 2303179 | MD Masfie Amin Srijon | Business idea and market problem | Problem Solution Fit, Value Proposition Canvas |
| 2 | 2303180 | Nafis Islam Kabbo | Business model and revenue strategy | Business Model Canvas, technology procurement |
| 3 | 2303127 | MRM Mubashshirul Haque | Internal strengths and weaknesses | SWOT internal |
| 4 | 2303148 | Refayet Hossain Ananda | External opportunities and threats | SWOT external |
| 5 | 2303174 | MD. Nafis Sadot | External business environment | PESTEL |
| 6 | 2303177 | Neloy Nandi | Competition and industry analysis | Porter's Five Forces |
| 7 | 2303181 | Anindo Chakma | Operations, people and risk management | Operations and Risk Analysis |
| 8 | 2303160 | MD Jebon Sheikh | Social impact, ethics and future strategy | Triple Bottom Line, Future Strategy |

## 7. Structure

48 slides: title, overview, eleven section dividers, thirty five content slides, closing. Section 4
carries four content slides because the risk argument is the part that most needs a diagram.

- **Slide 1, title.** Big AeroSetu wordmark, the standing descriptor, and a roll call of the eight
  presenters showing their section numbers and names. Nothing else. No strapline, no tagline, no
  "Rajshahi first" box, no counts line. The hero image on the right is `slide_one_hero.png`,
  supplied by the client.
- **Slide 2, overview.** Title is exactly **Overview**, subtitle is exactly **Presentation
  outline**. Section number in the left gutter, section title beside it, framework pushed to the
  right edge, one row per section, in three labelled columns. **No page or slide number appears
  anywhere on this slide.** The same header treatment is used on
  every page from slide 2 to the end.
- **Each section opens with a divider** carrying the minimal section title, the framework name and
  one claim the section has to land, plus a burgundy spine down the left edge. Dividers carry **no
  decorative section numeral**, **no presenter name** and **no "presented by" label**. The header
  eyebrow on the following slides already states the section number.
- **Final slide, thank you.** No names. Follow the earlier LLM deck: "Thank You", "Open
  Discussions", a line welcoming questions from the professor and audience, and three numbered
  discussion questions.
- **No references slide and no image credits slide.** The client supplies those separately.
  Citations stay short and on the slide where the claim appears.

## 8. Slide titles

- Titles are **declarative statements**, never questions.
- Avoid "Why", "Is it viable", "What happens if". State the finding instead.
- Good: "Predictability, not speed, is what customers pay for". Bad: "Why Tk 90 when a rider
  charges less".

## 9. Design rules

- **White background only.** No dark slides anywhere, including title and thank you.
- Palette from `LLM_Self_Correction_ICLR2024_Group_Presentation-final.pptx`: burgundy `#800020`
  primary, soft `#A24A48`, washes `#FFF1F2` and `#FDE8EA`, ink `#0F172A`, slate `#1E293B`, slate
  700 `#334155`, muted `#64748B`, forest `#166534` on `#F0FDF4`, amber `#B45309`, borders `#E2E8F0`
  and `#CBD5E1`, near white `#F8FAFC`.
- Colour is semantic: burgundy for our product and decisions, green for strengths and
  opportunities, amber for money, red for threats, weaknesses and AI prohibitions.
- Type: Century Schoolbook headers, Calibri body. Section divider numbers are set very large and
  in the palest burgundy tint, as a watermark behind the title.
- **12 pt is the absolute floor and only captions and source lines may use it.** Body text is
  14 pt or larger, card titles 16 pt, slide titles 32 pt.
- **Less text.** A three column card carries at most three bullets, each about 34 characters or
  fewer. No paragraph anywhere. Never more than about 55 words of body text on a slide.
- Every framework is a purpose built diagram, not a bulleted list.
- Section titles are minimal. The framework name does the describing.
- **Sections 3 and 4 are diagram led.** Section 3 opens with a left to right escalation flow with
  trigger labels on the arrows and a safety path running underneath all three tiers, then a
  two by two latency against capability map of the four architectures, then a cost share bar
  showing AI inference as a fraction of one hub. Section 4 opens with a probability against impact
  heat map carrying all nine risks as numbered dots.
- A diagram must survive being read from the back of a room. No diagram may rely on a legend alone,
  and no annotation may drop below 12 pt.
- Never an em dash or en dash anywhere.
- No raw URLs in the deck body.

## 10. Header, footer and slide numbering

- **Header, line one: the minimal section title, prefixed with its number**, for example
  `6. Internal strengths and weaknesses`. 14 pt bold, burgundy.
- **Header, line two: the sub title**, which changes on every page. 26 pt, shrunk a step for long
  titles.
- **The three header bands must never touch.** Fixed positions in inches: section line 0.20 to
  0.44, page title 0.48 to 1.02, kicker 1.04 to 1.32, content from 1.42. Do not move a band
  without moving the one below it.
- **Footer left, low on the slide: `Vision and AI powered drone food delivery`.** Always that
  string. It is not the brand name, not the section title, and it never varies.
- **Footer right, on the same low line: the page counter written as one unit**, `3/48`, not the
  number and the total in separate boxes. The number is a live PowerPoint `slidenum` field,
  injected by `build/slidenum.py`, so it renumbers itself when slides are inserted, moved or
  deleted. The total is static text, because PowerPoint has no total-slides field; if the client
  changes the slide count they must edit the total by hand.

## 11. Images

- Real, freely licensed photographs from Wikimedia Commons. **No AI generated imagery** as a
  substitute for evidence.
- Credit every photograph by author and licence. Keep `media/img/credits.json` in step with the
  files actually on disk.
- Never photograph an identifiable real person without consent.
- Drop images that read as stock filler, that show a competitor's branding, or that show the
  wrong subject.
- Rejected and not to be retried: consumer DJI product shots, courier vans with platform
  branding, generic building blocks, amateur toy drones, wilderness training footage, and
  anything carrying government branding.

## 12. Motion

- Native PowerPoint animation timelines cannot be written reliably. Do not claim otherwise.
- Motion is short silent MP4 with a real poster image drawn underneath, generated by
  `build/make_motion.py` from the deck's own photographs, plus one clearly labelled schematic.
- No third party drone video: none exists under a free licence that is both on message and free
  of government branding.

## 13. Facts and citations

- Every figure traces to a real citable source. Never invent a source or cite a document you have
  not confirmed exists.
- Accepted sources include CAAB, BTRC, BBS, IQAir, The Business Standard, The Daily Star,
  Dhaka Tribune, Rajshahi City Corporation, the World Bank, NBER, BRAC BIGD, Pathao, foodpanda,
  Zipline, BloombergNEF, BAPI, Z.ai and TypeSafe AI.
- Planning figures are labelled **Model assumption** on the slide.
- Short form citation on the slide where the claim appears, for example (Rajshahi City
  Corporation, 2020).

## 14. Output and versioning

- Never touch the existing LLM files in `output/`.
- Deck: `output/AeroSetu_Group_Presentation-vN.pptx`, from `-v1` up. The earlier
  `Drone_Food_Delivery_*` drafts have been deleted and must not be recreated.
- Speech: `speeches/full_presentation_speech.md`, one labelled section per presenter.
- Generator in `build/`. `generate.js` is the entry point, `slidenum.py` post-processes the
  counter, `make_motion.py` builds the video.

## 15. Quality check before delivery

Report the result of each, do not claim success:

- Every slide is white or photographic. Zero dark backgrounds.
- **No text below 12 pt**, verified by reading font sizes out of the generated XML.
- Body text is 14 pt or larger.
- Footer left shows exactly `Vision and AI powered drone food delivery`.
- Page counter reads `n/48` as one unit, the number is a live field, and it is confirmed by
  poisoning the cached values, rendering to PDF and checking PowerPoint recomputed all of them.
- Slide 2 is titled `Overview` with the subtitle `Presentation outline`, and lists all eleven
  sections.
- Slide 1 carries the wordmark, the descriptor and the roll call only, with `slide_one_hero.png`
  on the right.
- No "presented by" text and no presenter name on any divider.
- "SkyBhat", "As the crow flies." and "HUMANITIES GROUP PRESENTATION" appear nowhere.
- Every content page shows its section number and minimal title above its own sub title.
- Slide titles contain no questions.
- The last slide is a thank you with no names and no references or credits slides.
- All three technology tiers and the escalation order are present.
- Rajshahi first, Dhaka second, with the honest corridor weakness stated.
- All eight frameworks appear as purpose built diagrams.
- SWOT split correctly, internal in Section 7 and external in Section 8.
- Technology sits in its own Section 3, and the risk argument in its own Section 4, rather than
  being smeared across the business and operations sections.
- **Header air is checked:** the section line, the page title and the kicker occupy three separate
  bands with clear space between them and never touch.
- Every figure cited, every planning number labelled Model assumption.
- No em dash or en dash in deck, speech or captions.
- Risk register has at least eight risks with probability, impact and mitigation.
- Deck passes the pptx validator, and every slide has been visually inspected after rendering.
- Original LLM files untouched.

## 16. Out of scope

- Do not build the software, hardware or control system.
- Do not claim CAAB permission exists or is likely. Permission is a condition and it is the risk
  that can end the business.
- Do not claim medical, pharmaceutical or e-commerce contracts exist. The multi sector plan is a
  stated intention for later horizons, labelled as such.
- Do not claim the AeroSetu name is registered, and do not claim either model is a partner of the
  business.
