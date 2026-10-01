# AeroSetu: full presentation speech

Deck: `output/AeroSetu_Group_Presentation-v1.pptx`, 37 slides, 11 sections.
Timing: about 27 minutes at 140 words per minute. Roughly 3800 spoken words.
Eleven sections over eight presenters: Srijon, Kabbo and Mubashshirul each carry two, the rest
carry one. Read the slide number in brackets at the start of each block.

---

## Slides 1 and 2, opening

**[Slide 1]** Good morning. We are AeroSetu, a vision and AI powered drone food delivery business
analysis. The roll call on the right is our eight presenters and the sections each of us owns.
Eleven sections across eight people, so three of us are covering two.

**[Slide 2]** This is the shape of the talk. Section one is the problem and the market we enter,
section two is our value proposition. Section three is the technology, which is the part we are
most confident about and I will come back to it. Section four is technical safety and navigation
risk. Sections five and six are the business model and the money. Seven and eight are the internal
and external SWOT. Nine is competition and the industry landscape. Ten is operations and people.
Eleven is impact, ethics and where this goes next.

---

## Sections 1 and 2, MD Masfie Amin Srijon (2303179) — slides 3 to 7


**[Slide 3]** AeroSetu flies a corridor, not a route. An order is matched to a landing pad, the
drone launches from a hub, vision flies it down a corridor to the pad, it lands, and it returns.
What we sell is a promise, and the promise has a number in it: fifteen minutes, every time. The
customer also gets no rider sitting in traffic, and food that arrives hot.

**[Slide 4]** We start in Rajshahi, on purpose. This is not us avoiding Dhaka. Rajshahi has 553,288
people in the city at the 2022 census. Its urbanisation rate is 33 percent and growing near 8
percent a year. Four flyover projects worth about 490 crore taka began in December 2023 and every
one was still unfinished in September 2026. And on 16 March 2025 IQAir ranked it the most polluted
city in the country.

Now the weakness, because a plan that only lists strengths is not a plan. Rajshahi is less dense
than Dhaka, so our corridors run longer against a six kilometre range. That needs more pads per
corridor, and pads are capital. And RCC will ask hard questions about the university area. We still
start here, because a smaller regulator is a smaller bet.

**[Slide 5]** And the market is not a forecast. This is Dhaka's road tax, measured. Average journey,
74 minutes, for a trip a drone flies in six. 1.4 million trips a day, about a fifth of them now over
an hour. The average commuter loses four hours a day. Mean trip time has risen 0.6 percent since
2016 because the corridor space has been taken.

Rajshahi pays the same tax, smaller. This is a market that already exists, priced every day, in
lost time.

window.

**[Slide 6]** The Value Proposition Canvas. I will only claim one thing. The customer job is to get
hot food fast. The pain is traffic and uncertainty. The gain is time back in the day. Our product
is a corridor delivery and the pad it lands on. Our pain reliever is vision flying, because a
corridor is not a road, so congestion is simply irrelevant to it.

The claim we must defend is one line. A rider can be fast. A rider cannot be fifteen minutes,
every time, in rain, without a road.

**[Slide 7]** Problem Solution Fit, and I will be honest about it. Five of six dimensions are
genuinely proven. The problem is real and measured. The technology is demonstrated elsewhere. The
customer behaviour already exists. Revenue compares to existing platforms. The channel works, but
the pads are the barrier.

The sixth row is the context, and it says unproven in Bangladesh. Permission, monsoon, and a
regulator with no precedent. So the customer problem is solved, and the operating context is not.
That is exactly why we start small.

---

## Sections 3 and 4, Nafis Islam Kabbo (2303180) — slides 8 to 14


**[Slide 8]** This is the slide that matters most in our whole analysis. Vision does the flying. It
runs on the aircraft, always, and it handles navigation, obstacle detection, corridor following
and landing. It needs no network.

On top of that is an escalation chain. Jev is called only when a fast, bounded decision is needed.
It reads structured flight state and returns a typed action with a probability, so it can say
continue, reposition, abort landing, or return home. GLM-5.3-Flash sits above that, called only for
genuinely ambiguous situations where you want multimodal reasoning.

The frequency is what makes this affordable. Vision runs on every flight. Jev runs on most
decisions. GLM runs on a small minority.

And look at the green bar. Hard safety rules, state estimation, path planning and flight control
are always local and deterministic. If the link drops mid flight, the aircraft finishes vision only
and lands. A network outage is a slower delivery. It is never an unsafe one.

**[Slide 9]** Four architectures, plotted on two axes: how fast the answer comes back, and whether
the system can handle the genuinely hard case. Vision only is cheap and fast and blind in exactly the
situations that matter. Vision and GLM covers it, but slowly, and it burns reasoning tokens on easy
calls, which is paying a specialist to read a menu. Vision and Jev is fast and cheap but has no
answer when a case is genuinely strange. There is exactly one point high on capability and low on
latency at the same time. That is the one we build.

**[Slide 10]** And the model choice, made for business reasons rather than benchmark scores.

GLM-5.3-Flash, from Z.ai. MIT licence, weights ungated on Hugging Face, commercial use permitted.
About 0.075 dollars per million input tokens and 0.25 per million output. Its intelligence index is
57, against a median near 27 for open weight peers its size. And we cap the reasoning effort, so a
hard flight cannot bill us without limit.

Jev, from TypeSafe AI. Here I have to be straight with you. It is proprietary and hosted, with no
public weights, so we cannot self host it. About 0.0029 dollars per thousand decisions on the
vendor's own estimate. And it is genuinely the right tool, because it returns a typed action with a
probability that a flight path can act on directly. But we are accepting vendor lock in on our
fastest tier, and a licence change would force a rebuild.

The decision in one line: one vendor we own, because we can host and fork GLM. One vendor we rent,
because Jev is fast and cheap but closed.

trigger is only a worry.

**[Slide 11]** All nine risks on one map, probability against impact. Look at the top row. Risks one
and two sit in the same square: CAAB refusing permission, and a corridor crossing restricted airspace.
People treat these as two items. They are one risk seen from two directions, and both are asking the
same question, which is whether we are allowed to fly at all.

Risk five is the one that bites us in year one, vision failing in heavy rain, and our answer is
weather thresholds that stop launches outright. We would rather fly nothing in July than fly badly.

**[Slide 12]** The register itself, first five. CAAB refuses permission, medium and severe, mitigated by a
pre-application meeting first and no hardware ordered before a written response. Corridor crosses
restricted airspace, medium and severe, mitigated by an altitude cap and re-routing verified on map.
Aircraft lands outside a pad, low and severe, mitigated by on-board pad recognition and a local
geofence. Liability dispute, medium and high, mitigated by insurance and a host contract clause.
Vision fails in heavy rain, high and high, mitigated by weather thresholds that stop launches
outright.

Risks one and two are the same risk from two sides: whether we are allowed to fly at all.

**[Slide 13]** Risks six to nine, operating and commercial. Battery degradation, Jev withdrawn or
repriced, pad host withdraws consent, rider or customer refuses a pad. None is fatal alone.

But risk seven is the one people forget, and it is in the box. We chose a closed model for our
fastest tier, and we accept that. The mitigation is not a contract. It is a rule set that works
without Jev.

over a crowd, so corridors are sized never to cross a school, hospital or stadium, with no exception
and no launch. No flight without a recoverable pad, so if the pad is not recognised the aircraft
does not descend, it holds and returns home. And no model on the safety path, so safety rules, state
estimation, planning and control stay local and no network call can unlock a flight.

These are not on a roadmap for improvement. They are the reason a regulator might listen at all.

---

## Sections 5 and 6, MRM Mubashshirul Haque (2303127) — slides 15 to 19

break even.

**[slide 19]** The Business Model Canvas. I will not read all nine blocks. The three that matter are
the bottom row. Customer segments is urban households ordering three or more times a week. Cost
structure is airframes, hubs, pads, staff, insurance, connectivity and AI inference. Revenue is
delivery fee, subscription, kitchen contract, and later corridor data.

**[Slide 15]** Six revenue streams, and the order matters. Delivery fee at 90 taka, from day one.
Subscription at 499 a month from month six, and this is the one that changes the maths, because
five flights a month turns a cost into a habit. Kitchen contract at six to ten percent from month
nine. Pad hosting at 400 a month from month nine, which pays for the pad on the customer's roof.
Corporate and NGO in year two. Corridor data in year three.

Only the first two are needed to reach break even. Delivery fee alone has to cover airframe life,
not just fuel, and that is why we cannot go below 90 taka.

of that number.

**[slide 22]** One hub, one month, itemised. This is the number that decides whether the business
exists. Airframe lease for six aircraft, 180,000. Hub rent and utilities, 120,000. Salaries for nine
staff, 270,000. Batteries, 60,000. Connectivity and cloud, 25,000. AI inference at launch volume,
18,000. Insurance and maintenance, 40,000. Building forty pads at 4,000 each, 160,000.

Total: 873,000 taka per month, per hub. Every one of these is a model assumption. But note the AI
line. Eighteen thousand taka a month for the intelligence that flies the aircraft. That is not an
accident, and Nafis already explained why.

**[Slide 17]** Unit economics. Per delivery, in Rajshahi, at launch volumes. Fee collected, 90. Pad
hosting net, 20. Variable cost, 46. AI inference, 1 taka. That gives a contribution of 43 taka per
flight.

So how many flights does a hub need? 20,290 taka of monthly fixed cost. 471 flights a month. 16 a
day across six aircraft. And three per aircraft per day, which leaves room for weather.

20,600 against 20,290 of fixed cost. Operating result, 310 taka a month. That is break even, on a
thin margin. In Dhaka at 34 flights a day, contribution is 44,000, and the operating result is
23,700.

So we reach break even in Rajshahi with almost no cushion, and in Dhaka with room to survive a bad
month. We launch in the hard city to learn cheaply, and we scale in the dense one to earn. And the
honest limit is on the strip: below twelve flights a day, a hub loses money. Density is the
constraint, not demand.

---

## Section 7, MD. Nafis Sadot (2303174) — slides 20 to 22

**[Slide 19]** I am Nafis Sadot. I own the internal SWOT. Knowing our own limits is the cheapest
advantage we can buy.

**[slide 26]** Internal strengths, and only things we genuinely control. Vision-first architecture,
so the safety path never needs a network. Escalation design, so the costly model runs on a minority
of flights. Corridor instead of road, so the promise does not depend on traffic. Pad-based landing,
so we land somewhere we control. A local cost base, because Rajshahi rents and salaries are well
below Dhaka. And founder operator access, because we can design corridors and negotiate pads
ourselves.

**[Slide 20]** Now the weaknesses, stated plainly, because a SWOT that flatters itself is useless.
No operating history and no CAAB approval. No regulatory precedent. Capital hungry, because pads
and hubs are paid for long before revenue. Weather exposure. Model dependency on a closed vendor.
And a team of eight with no dedicated safety engineer, no legal counsel, and no regulator relations.

The right-hand column is what matters. Against no approval, we get a pre-application meeting before
we order hardware. Against capital hunger, one hub and two corridors, not a city-wide plan. Against
model dependency, a deterministic rule set that reproduces Jev's decisions without it.

that is provably safe. Escalation needs two models behaving as tested. Corridors need pads, and pads
need permission. Pad landing needs the host to stay. The local cost base gives us a thinner margin
if volume is low. And eight founders create key person risk.

The fourth column is how we hold each one. A strength without a limit is optimism.

---

## Section 8, Refayet Hossain Ananda (2303148) — slides 23 to 25

**[Slide 22]** I am Refayet. I own the external SWOT. And the regulator is the largest single factor
in this business.

**[slide 30]** Opportunities. The road problem is already measured. Delivery demand is compounding,
and the ceiling is not in sight. Bangladesh is ready for drone policy, because the National Drone
Policy 2026 framework exists. The last mile is unreliable in peripheral areas, leaving demand roads
cannot serve. Pad and rooftop space suits a pad model better than a tower-block city. And corporate
and NGO demand already travels by road at high cost and low speed.

means no flights and a hardware company with no revenue. A platform price response, where Pathao or
foodpanda can subsidise below our cost. Airspace conflict. Monsoon shutdown, and the worst month for
air is the worst month for road demand too. A public safety incident, because one accident ends the
conversation with the regulator. And liability exposure, which we have not settled.

**[Slide 24]** So eight threats, eight owners, and a trigger for each one. A CAAB refusal is watched
by the founder and the CAAB liaison, triggered by a written refusal or ninety days of silence. A price
response is watched by partnerships, triggered by a platform fee below 40 taka on our corridor.
Monsoon is watched by operations, triggered by four consecutive no-fly days.

That is the difference between a SWOT and a plan.

---

## Section 9, Neloy Nandi (2303177) — slides 26 to 28

**[Slide 25]** I am Neloy. I own competition and the industry landscape. We are not competing with
riders. We are competing with a road.

**[slide 34]** But before the competition, the industry has no rules yet, and that shapes everything
else. Four questions we cannot answer. Who authorises delivery flight, given CAAB holds airspace but
no delivery licence class exists. Over what height, and over whose land. Who issues an operator
certificate, because we are not pilots so the rule that applies to us is not written. And what the
liability position is.

The only responsible answer today is in the box. We have not been granted permission and we do not
assume we will be. The first milestone is a written pre-application meeting with CAAB. Until that
document exists, our financial plan is a hypothesis, and every slide in this deck says so.

**[Slide 26]** Five forces. Rivalry is high, because Pathao and foodpanda fight for orders and can
subsidise below our cost. Substitutes are high, because a rickshaw, a car and walking are all
substitutes, and only the fixed window is unsubstitutable. Buyer power is high, because the customer
holds one tap and no contract.

Supplier power is low, because batteries are replaceable and open weights reduce supplier power. New
entrants are medium: hardware you can buy, pads and corridors you cannot.

Three of five forces are high. That is why this is not a discount business. Rivalry, substitutes and
buyer power are all set by the customer, not by us. Our only lever is the pad network and the fixed
window it makes possible.

**[Slide 27]** Which is the moat. An entrant would have to copy four things. Sign pad hosts, months of
negotiation one roof at a time. Get CAAB permission. Design a corridor. And prove the window, which
takes hundreds of deliveries.

Airframe is buyable in six months with capital. Software is buyable and open weights are free. But
the pad network is slow, CAAB approval is slow, and proven corridor data is very slow. Those three
are strong.

---

## Section 10, Anindo Chama (2303181) — slides 29 to 31

**[Slide 28]** I am Anindo. I own operations and the people system.

**[slide 38]** One order, eight handovers. Placed, kicked off, loaded, launched, corridor flight,
approach, landing, returned. Each has a named owner. And the rule that governs every handover is the
green box. The aircraft decides its own safety and may refuse a landing at any step. A refused
landing means return home, a rebooked order, then a refund. And no operator, customer or model can
override the safety path on board.

**[Slide 29]** The people. Nine roles in the pilot hub. Hub manager, flight operations lead, safety
lead, corridor engineer, AI and data lead, two line mechanics, kitchen coordinator, customer support,
regulatory affairs.

Three of these are new to a delivery business, and none of the three are optional in Bangladesh. A
safety lead, because the safety path needs an owner who is not the person selling flights. An AI and
data lead, because escalation thresholds and drift need someone accountable. And regulatory affairs,
because CAAB applications and insurance do not run themselves.

**[Slide 30]** And this is escalation as an operating procedure, because it belongs with operations
rather than with the architecture. Vision only when the obstacle is clear, the pad is free and weather
is inside limits. That always happens on board. Vision to Jev when the pad is occupied, the approach
is degraded, or confidence is below the floor. That is most decisions. Jev to GLM when the case is
ambiguous or unlike training. That is rare. And the safety path, when any hard limit is crossed or
the link is lost, is a deterministic return. That is never escalated.

---

## Section 11, MD Jebon Sheikh (2303160) — slides 32 to 36

answers to its balance sheet is not a business we want to run.

**[slide 42]** Triple bottom line. People: riders lose the worst trips on the network, a pad income
for households that own a roof, and fewer injuries because fewer road kilometres. Planet: no tailpipe
emissions and less fuel burned, against rotor noise as a cost paid in goodwill. Profit: a fixed
window the platforms cannot match, contribution that scales with corridors, and a regulator who can
say no at any time.

The trade we accept is in the box, and it names who pays. Riders lose the highest paying, worst
paying, most dangerous trips if we take the easy ones first. We will take them deliberately and
slowly, and we will publish what it costs the rider who loses one. People first is only credible if
it names who pays for it. The riders pay, so the riders are in scope.

**[Slide 32]** Five ethics commitments we would publish, written before launch rather than after
criticism. No flight over a crowd. The aircraft may refuse. Pad consent is renewable on thirty days
notice. Riders keep their income floor, so corridor assignment never drops anyone below their current
daily average. And every incident is disclosed, to the customer, the pad owner and the regulator, in
that order.

**[Slide 33]** Ethics of the AI specifically, five limits we will not cross whichever model is in the
loop. No model commands a flight, because models recommend and control stays local. No training on
customer data. Every decision is logged, including vision output, Jev action and GLM
recommendation. Confidence is respected, so below the floor the system abstains rather than guessing a
landing. And human escalation has authority, because a supervisor can stop any flight and the
aircraft will not argue.

Rule zero is in the green strip: the drone must be safe to fly with no network, no model and no
data.

**[Slide 34]** Three horizons. Horizon one, months zero to six: CAAB pre-application answered, one
hub, two corridors, forty pads, vision only with Jev behind a flag. Horizon two, six to eighteen
months: written permission in hand, Jev and GLM live on escalated flights, break even on one hub.
Horizon three, years two and three: Dhaka corridors, three more hubs, medical and blood contracts,
corridor data sold as a product.

Permission gates Horizon two and break even gates Horizon three. Neither can be bought ahead of the
other. And note the strip: Rajshahi is Horizons one and two, Dhaka is Horizon three.

**[Slide 35]** So six conditions, and the verdict. CAAB grants corridor permission, binary, not yet.
A hub flies sixteen deliveries a day against twelve needed, not yet. Contribution holds above 40
taka, we model 43, not yet. Landing on a pad rather than a rooftop, not yet. Escalation keeps AI cost
under 1 taka a flight, not yet. And monsoon does not close the network, not yet.

Six of six are untested, and that is the honest position of any first year. The plan is not to prove
the market, because the market is already proven. It is to prove permission and density, in
Rajshahi, before any capital is committed to Dhaka.

---

## Closing, slide 37

**[Slide 36]** Thank you. We welcome questions from the professor and audience, and we have left
three on the slide that we would most like to be asked. Thank you.