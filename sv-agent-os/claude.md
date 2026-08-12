# SV Agent OS — Master Context

This is the root context file. It points to everything else. Read this first, then load
only the files relevant to the task at hand.

## What this is

A working knowledge base for running an Amway business focused on the **eSpring water
purifier**, plus the tools used to explain that business to two different audiences:

- **Reps** — people who might build the business themselves (sell units, build a team)
- **Partners** — people who might refer, host, or plug in at a lighter level

## Directory map

```
sv-agent-os/
  claude.md                              ← you are here
  memory.md                              ← living log; update after real conversations
  context/
    business_info.md                     ← who we are, what we sell, how we operate
    brand_voice.md                       ← how we sound, what we never say
    amway_compensation_plan.md           ← how income is actually calculated  ★
    espring_product.md                   ← the product itself
    yeager_group.md                      ← our line of affiliation, system, events
    compliance_and_income_claims.md      ← rules for showing income numbers  ★ READ BEFORE PRESENTING
  partners/
    context/icp.md                       ← who a good partner is
    skills/qualification_process.md      ← 8-step, MG1, objections
  reps/
    context/icp.md                       ← who a good rep is
    skills/sales_script.md               ← NEPQ, PFAS opener, onboarding
  tools/
    espring_income_calculator.html       ← the thing you open in front of someone  ★
    README.md                            ← how to use and verify the calculator
```

★ = load these before any income conversation.

## The core use case this was built for

Sitting across from someone and showing them, concretely:

> "If you sell ten eSprings a month, here is what that pays you. If you have ten people
> also selling ten a month, here is what *that* pays you — hourly, weekly, monthly, yearly."

The tool that does this is `tools/espring_income_calculator.html`.

## Non-negotiable rule

**Never show income figures without the current Amway Income Disclosure Statement
alongside them.** This is not optional politeness — it is required by Amway's Rules of
Conduct and by FTC rules on earnings claims. See `context/compliance_and_income_claims.md`
before any presentation. A compliant presentation is also a more persuasive one, because
the person across from you can tell you are not hiding the downside.

## Status of the numbers in this repo

The calculator ships with **placeholder rates**, not verified Amway figures. They exist so
the math engine has something to chew on. Before this is used with a real person, every
price, PV, BV and bonus percentage must be replaced with current official numbers from
your own Amway materials. See `context/amway_compensation_plan.md` for the checklist of
exactly what to look up and where.
