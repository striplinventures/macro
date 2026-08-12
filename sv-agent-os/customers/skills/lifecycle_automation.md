# Skill: Customer Lifecycle (Texts, Email, Social)

**Status: designed, not built.** Nothing here is automated yet. Right now this is
the manual sequence — run it by hand and log what lands in `../../memory.md`. When
it gets automated, this file is the spec the automation implements.

**Use this when:** a customer has bought an eSpring, or when building/reviewing
the follow-up sequence.

**Done looks like:** the customer is installed, using the product daily, reachable
on a consented channel, and has been asked for a referral once, after a positive
experience check — not before.

## What gets captured at the sale

The VCS requirement and the follow-up sequence need the same data, so capture it
once, at the sale:

| Field | Why |
|---|---|
| Name | VCS requirement |
| **Unique mobile number** | VCS requirement + SMS channel |
| Email | Email channel |
| Install date | Times the whole sequence |
| Address / zip | Which local water story applies to them |
| Who sold it | Rep attribution; routes their questions to the right person |
| Consent — SMS | Legally required before any automated text |
| Consent — email | Required before marketing email |

VCS also needs the product and retail price recorded — see
`../../context/compensation_plan.md`.

## Consent rules — these are not optional

- **Opt-in before send.** Explicit, recorded at the point of sale, separately for
  SMS and email. "They gave me their number" is not consent to text them.
- **Every message identifies who it's from** and gives a way to stop — STOP for
  SMS, unsubscribe for email.
- **Honor an opt-out immediately** and permanently, across both channels if
  that's what they asked for.
- **Service ≠ marketing.** An install check-in is service. A referral ask is
  marketing. Keep the consent for each straight, and when in doubt treat it as
  marketing.
- Amway compliance still applies to every message: never lead with Amway, no
  income claims, no independent branding of Amway products, education before
  product, engage rather than broadcast. Full rules in
  `../../context/business_info.md`.

## The sequence

Timing runs from the **install date**, not the purchase date.

| When | Channel | Purpose | Content |
|---|---|---|---|
| Day 0 | Text | Confirm | Thanks, install date confirmed, who to text with questions. |
| Day 1–3 | Text | First taste | "How's the water tasting?" One question, easy to answer. |
| Day 7 | Email | Get it used | How to get the most out of it day to day. No ask. |
| Day 14 | Text | Experience check | Open question about what's changed at home. **This is the gate for the first referral ask.** |
| Day 30 | Email | Social + story | Invite to follow SV socially; offer to share their story if they're willing. |
| Day 45 | Text | Referral ask | Only if day 14 came back positive. See `referrals.md`. |
| Day 90 | Text | Still using it? | Catches the drop-off. If usage stalled, that's a service problem to solve, not a moment to sell. |
| Filter due | Text + email | Replacement reminder | Timed to the cartridge life stated in the Owner's Manual. **Confirm that figure from the manual before scheduling — do not estimate it.** |
| Annual | Email | Water check-in | Any new local water news relevant to their zip. Education, no pitch. |

## Writing rules for these messages

- **Texts are one question long.** If it needs two paragraphs, it's an email.
- Lead with the water, not the product. We check on their household's water, not
  on an appliance's performance.
- Use their local specifics — utility name, the measured figures in
  `../../reps/skills/sales_script.md` — and nothing beyond that list.
- No hype, no urgency theater, no income talk. Brand voice rules in
  `../../context/brand_voice.md`.
- A service message never carries a business pitch. If a customer looks like a
  rep or partner candidate, that's a separate conversation on a separate day —
  see the upgrade path in `../context/icp.md`.

## Social

The day 30 email is the only scheduled social ask. Point it at following SV, not
at resharing product posts — engage, don't broadcast. Customer stories get used
only with explicit permission, and a customer's story is about their water, never
about money.

## Before this gets automated

Open decisions, none of them made yet:

1. **What tool sends it.** No platform picked. Whatever it is has to hold consent
   state per channel and honor opt-outs across both.
2. **Where customer records live.** Right now the VCS data lives in Amway's
   tooling. The sequence needs a record with install date and consent flags — the
   two systems need one source of truth, not two.
3. **Who answers replies.** Every message in this sequence invites a reply. An
   automation that sends but doesn't listen is worse than sending nothing.
4. **Rep-sold customers.** Does the rep run their own follow-up, or does this
   sequence run centrally with the rep's name on it? Decide before scaling past
   the first few reps.
