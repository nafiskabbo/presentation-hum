# Sections 3 and 4, spoken script

**Presenter:** Nafis Islam Kabbo (2303180)
**Sections:** 3. Technology: Vision, Jev and GLM · 4. Technical Safety and Navigation Risk
**Slides:** 8 to 14 of `output/AeroSetu_Group_Presentation-v1.pptx`
**Length:** about 6 minutes, 950 spoken words

Read the stage directions, not the slide. The questions in this file are there to be asked out loud,
to the room, and then answered by you. They are marked `Q:`.

---

## How to land this section in one line

If the room remembers one thing from you, make it this: **we spend our AI budget on the flights that
are actually hard, and nothing on the ones that are easy.**

Everything below supports that sentence.

---

## Section 3 opener

Take a breath here. This is the start of your two sections.

> "Vision does the flying. The models are called only when a decision is hard."

---

## Slide 8, the escalation architecture

Walk left to right along the three blocks, then drop your hand to the green bar underneath.

> Every flight starts on the aircraft. Vision handles navigation, obstacle detection, corridor
> following and the landing. No network, no model, no excuses. It runs on every single flight.

> Then there are two more tiers, and this is the part people find surprising. **Jev** is not a chat
> model. It never writes a sentence. It reads structured flight state and hands back a typed action
> with a probability attached. Continue. Reposition. Abort the landing. Return home. That is the whole
> vocabulary, and it returns it in milliseconds.

> **Q: Why pay for something that is not even an LLM?**
>
> Because a pilot does not need a poem to decide whether the landing pad is occupied. They need a
> fast, typed, checkable answer. Jev is that answer. Every word an LLM generates is a word we pay for,
> wait for, and then have to parse. Jev skips all three.
>
> Think of it like this: Jev is the **conductor**, not the orchestra. It does not play the violin. It
> cues the sections and knows which players come in when.

> Above everything runs the green bar, and this is the rule we will not bend. Hard safety rules,
> state estimation, path planning and flight control are local and deterministic. **If the network
> dies mid flight, the drone finishes vision only and lands.** A dropped connection is a slower
> delivery. It is never an unsafe one.

> The expensive model is the exception, not the rule. That is the whole design.

**If you are running short on time, this is the slide to shorten.** Cut the orchestra line, keep the
network line.

---

## Slide 9, four architectures plotted

> Before we built it we drew the options on two axes: how fast the answer comes back, and whether
> the system can handle the genuinely hard case.

> Vision on its own is cheap and fast, and it is blind in exactly the situations that matter. Vision
> plus GLM handles the hard case, but it is slow and it burns reasoning tokens on easy calls, which
> is paying a specialist's fee to read a menu. Vision plus Jev is fast and cheap, but it has no
> answer when a case is genuinely strange.

> There is exactly one point on this chart that is high on capability and low on latency at the same
> time. That is the one we build.

**Q: So are we paying for three models?**
>
> No. We are paying for one model, and we are only paying for it when we have to.

---

## Slide 10, GLM and Jev on licence and cost

> Now the commercial case, because a technology choice that cannot be justified on a spreadsheet is a
> hobby.

> **GLM-5.3-Flash**, from Z.ai. MIT licence, weights ungated on Hugging Face, commercial use
> permitted. That means we can host it ourselves, fork it, and nobody can raise the price on us or
> pull it away. Its intelligence index is 57 against a median near 27 for open weight models its
> size. And we cap the reasoning effort, so one genuinely difficult flight cannot send us a bill we
> did not agree to.

> **Jev**, from TypeSafe AI. And I want to be straight with the room here, because this is a
> dependency we are choosing to accept, not one we can ignore. It is proprietary and hosted. There
> are no public weights. About 0.0029 dollars per thousand decisions on the vendor's own estimate,
> which is cheap. But if the licence changes tomorrow, we would have to rebuild our fastest tier.

> So the honest summary is one sentence: **one vendor we own, because we can host and fork GLM, and
> one vendor we rent, because Jev is fast and cheap but closed.**

> And look at the bar at the bottom. That is what the intelligence actually costs us: about 2 percent
> of one hub. Escalation is what keeps it there.

---

## Section 4 opener



---

## Slide 11, the nine risks plotted

> Nine risks, plotted by probability against impact. The colour gets worse as you move up and right.

> Look at the top row. Risks 1 and 2 sit in the same square: CAAB refusing permission, and a corridor
> crossing restricted airspace. People treat these as two separate items. They are one risk seen from
> two directions, and it is the same question both times: **are we allowed to fly at all?**

> Risk 3 is low probability and severe impact. The aircraft landing somewhere that is not a pad. We
> mitigate it on board, not in a policy document.

> Risk 5 is the one that will actually bite us in year one. Vision failing in heavy rain, high
> probability and high impact. Our answer is weather thresholds that stop launches outright. We
> would rather fly nothing in July than fly badly.

> And risk 7 is the one nobody puts on a heat map, so I will say it out loud: **Jev is withdrawn or
> repriced.** Medium and medium. And it is the dependency we just chose on the previous slide.

**Q: If Jev disappeared tomorrow, what happens?**
>
> The aircraft does not stop being safe, because Jev was never on the safety path. We keep a
> deterministic rule set that reproduces its decisions. We fall back to GLM, which is slower and
> dearer. And we rebuild. That is the whole plan, and it is why the green bar on slide 8 matters.

---

## Slides 12 and 13, the register

Do not read these tables aloud. Say the shape of them and move on.

> The register gives every risk a probability, an impact and a mitigation we can actually run. Risks
> one to five on this slide, six to nine on the next. Every mitigation is something a named person
> does on a date, not something we hope happens.

> The one worth naming is risk four, liability over a roof. We land on somebody's property. That is
> an insurance question before it is an engineering one, and it is not solved yet.

---

## Slide 14, the three prohibitions

Slow down. This is the most important slide in my section.

> Everything so far has been a trade-off. These three are not. They are prohibitions, and they are not
> on the roadmap for improvement.

> **One. No flight over a crowd.** Corridors are sized so that a corridor never crosses a school, a
> hospital or a stadium. No exception, no launch.

> **Two. No flight without a recoverable pad.** If the aircraft does not recognise the pad on board,
> it does not descend. It holds, and it returns home. We would rather lose the delivery than the
> customer's air conditioner.

> **Three. No model on the safety path.** Safety rules, state estimation, planning and control stay
> local. No network call can unlock a flight.

> And the whole section comes back to one line: **the aircraft is always allowed to refuse, and no
> model and no manager can tell it to continue.**

> These three are the reason a regulator might listen at all.

---

## If the audience asks you something you did not cover

| Question | Short answer |
|---|---|
| Why not use one strong model for everything? | Because a strong model on an easy decision is slow and expensive, and we would be paying reasoning prices for a yes or no answer. |
| Is Jev actually available to us? | It is early access and hosted. We have not signed anything, and we flag it as a dependency. |
| What if GLM is down? | Jev covers most decisions, and vision covers the safety path. A GLM outage costs us the rare hard cases, not safety. |
| Why escalate at all, why not just vision? | Vision cannot judge an unfamiliar situation. Escalation is how we keep the cost of that judgement off every flight. |
| Does the model ever overrule the pilot? | Never. There is no override path. The safety path is local and deterministic. |
| What is the AI cost per flight? | About 1 taka, on a 90 taka delivery. It is 2 percent of a hub. |

---

## Delivery notes

- Three questions are built into this script: the LLM question on slide 11, the three models question
  on slide 12, and the Jev disappearance question on slide 15. If time is short, cut slide 12's
  question, not slide 15's.
- The orchestra line and the menu line are your two easy wins. Say them slowly.
- Do not read the tables on 12 and 13. Markers penalise reading aloud; they reward shape and
  ownership.
- Land the section on the three prohibitions, not on the register. That is the part that sticks.