# Web Platform

The public site and the software behind it. Read this before assuming something
needs to be built — several things in this OS are already running here.

## The site

| | |
|---|---|
| Live | `striplinventures.lovable.app` |
| Built on | Lovable, project `cf0c1f72-a498-4efb-88e1-fd1b4c121f77` |
| Editor | `lovable.dev/projects/cf0c1f72-a498-4efb-88e1-fd1b4c121f77` |
| Stack | TanStack Start (TypeScript) + Supabase + Tailwind |
| Design tokens | `src/styles.css` — mirrored in `brand_voice.md` |

**What the site is:** a PFAS and water-quality education page that funnels people
into a consultation. It carries local water-quality information, the data-center
angle for NW Georgia and SE Tennessee, the Erin Brockovich connection, a personal
story section, install imagery, certifications, and a lead form. There's a
Spanish route (`/es`) and a language switcher.

**Content routes:** `/` · `/es` · `/privacy` · three blog posts — is Dalton GA tap
water safe, do fridge filters remove PFAS, whole-house water filter cost in NW
Georgia · plus `sitemap.xml` and `llms.txt`.

**Authenticated routes:** `/auth`, `/partner` (referral portal), `/admin`
(pipeline management, gated by a `has_role` admin check).

## The referral pipeline — already built

This is live software, not a plan. A logged-in referrer submits a referral and it
lands in Supabase.

**What a referral record holds:** referrer ID, client name, client phone, client
email, client city, notes, stage, bonus status, timestamps.

**Stages:** `new → contacted → demoed → tested → closed_won` / `closed_lost`

Note that **demoed** and **tested** are separate stages — the pipeline already
encodes the demo stack and the dip test as distinct steps, which matches
`../reps/skills/sales_script.md`.

**Bonus status:** `pending → earned → paid`

**Notifications that already fire:**

- New referral submitted → notifies on the referrer's email.
- Stage flips to `closed_won` with bonus `earned` → notifies the referrer that a
  bonus was earned.

**Permissions:** a referrer sees only their own referrals; listing everything and
changing stage or bonus status requires the admin role.

**MCP tools the site exposes:** `submit-referral`, `update-referral`,
`list-my-referrals`, `list-all-referrals`, `list-leads`, `list-opportunities` —
so an agent can work the pipeline directly rather than through the UI.

## Naming collision — watch this

The site calls anyone who submits a referral a **"partner"** (`partner_user_id`,
the `/partner` route). In this OS, **partner** means a Yager business partner who
went through the full qualification process.

They are not the same thing. A plumber submitting referrals is a **rep** in OS
terms and a "partner" in site terms. When reading site data or writing about it,
say which sense you mean. Renaming one of them would remove a permanent source of
confusion.

## What this changes about the customer track

`../customers/skills/lifecycle_automation.md` lists four decisions blocking
automation. This platform already answers part of them:

- **Where records live:** Supabase, here. It doesn't yet hold eSpring owners as
  such — the `referrals` table is a pipeline of prospects, not a customer list
  with install dates and consent flags.
- **What sends messages:** email sending already exists on the server
  (`email-send.server.ts`, plus lead and referral notifiers). **No SMS channel
  exists yet** — every text in the lifecycle sequence is still unbuilt.
- **Consent:** the referral schema captures name, phone, email, and city. It does
  **not** capture SMS or email consent. That field has to exist before any
  automated send.

## Other projects in the StriplinHub workspace

Context for what already exists, so nothing gets rebuilt from scratch:

| Project | What it is |
|---|---|
| StriplinVentures PFAS | The live site above |
| SV PFAS Landing Page | Earlier standalone landing page |
| Remix of StriplinVentures PFAS Landing | A remix of the landing page |
| AquaRoute CRM | RepCard-style D2D CRM — map, house dispositioning, appointment tracking |
| Dream Clock | SV-themed clock in/out tied to the #10 lifestyle, with accumulated hours |
| Contractor Agreement Builder | Generates the independent contractor agreement (docx) |
| Secure Partner Agreements | Same family — QA representative contractor agreements |

**AquaRoute CRM is worth a second look** before building anything new for rep
tracking — dispositioning and appointment tracking is exactly what the rep track
needs, and it already exists in draft.

The two agreement builders use a different magenta (`#B5117E`) than the brand
(`#F235A0`). One of them is wrong; the site is the source of truth.
