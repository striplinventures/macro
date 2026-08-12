# Tools

## `espring_income_calculator.html`

An interactive, self-contained page for showing someone how the Amway compensation plan
calculates income at a chosen level of eSpring sales. No install, no internet, no
dependencies — open the file in any browser, or use the hosted link if one has been
published.

### First-time setup (do this once, before you use it with anyone)

1. Open the file. You will see an orange **unverified rates** banner.
2. Expand **Plan Rates**.
3. Replace all four eSpring figures — retail price, your IBO cost, PV, BV — with the
   current numbers from your Amway back office.
4. Check every row of the Performance Bonus schedule against your current Business
   Reference Guide. Edit any that are wrong.
5. Tick the confirm box. The banner disappears.

Values are not saved between sessions — the page resets to placeholders on reload. Either
redo step 3–5 before each meeting, or edit the defaults directly in the file (search for
`value="1400"` and the `DEFAULT_SCHEDULE` array near the top of the `<script>` block) so
your verified numbers load every time. Editing the defaults is strongly recommended once
you have confirmed them.

### Using it in a meeting

The top section is the one to show. Set:

- **Units you sell/month** — the scenario, usually 10
- **People on your team** — usually 10
- **Units each of them sells** — usually 10
- **Hours you work/week** — this is what turns the result into an hourly figure

Two panels appear side by side: **Just you** and **You + your team**, each showing monthly,
yearly, weekly and hourly. Below them, *Where the money comes from* breaks the total into
retail margin, your own Performance Bonus, and the differential on team volume.

The **Plan Rates** panel is collapsed by default so you are not showing the guts of the
calculation while you talk. Expand it if someone asks — being willing to open it is worth
more than the number itself.

### The conversation that goes with it

Lead with the mechanism, not the total. The number that persuades an honest person is not
"$7,315" — it is understanding *why* ten people selling ten is worth more than eleven times
one person selling ten. The `mathNote` line under the breakdown says it in one sentence:
your team keeps their own bracket, you earn the spread, and the group volume lifts your
bracket.

Then name the assumptions before they do. See
`../context/compliance_and_income_claims.md` for the six that matter and the language to
use.

### Non-negotiable

Do not present any figure from this tool without the current **Amway Income Disclosure
Statement** in hand. The page carries the disclosure text at the bottom; that text is not
a substitute for the actual statement.

### Printing

The page prints cleanly — input controls and the rates panel are hidden, results and
disclosure are kept. Use `Ctrl/Cmd-P` if you want to leave something behind.
