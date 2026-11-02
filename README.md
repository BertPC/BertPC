# Erik Bertrand

Senior full-stack engineer on Cape Cod, Massachusetts. Twenty-five years building for
the web, fifteen of them in enterprise engineering at Dyn and Oracle. I now run
[Ascent Web Solutions](https://ascentwebs.com), a boutique web studio, and built and
released [SyteCheck](https://sytecheck.app), a website-analysis SaaS product of my own.

I write Python, TypeScript, React, and PHP, work in Linux and cloud infrastructure,
and care more about what a system looks like in five years than what it looks like on
launch day.

**Currently open to:** contract engineering engagements, permanent roles, and website
projects for businesses and organizations.

---

## What I'm looking for

Three separate things, and I'm happy with any of them.

- **Contract engineering.** Agency overflow, fixed-scope builds, migrations, and
  integration work. Remote, US Eastern, used to being the only engineer on a
  distributed team.
- **Permanent roles.** Mid- or senior-level full-stack, platform, or infrastructure
  work. Remote, or hybrid within reach of Cape Cod in Massachusetts.
- **Website projects.** Fixes, refreshes, and rebuilds for small businesses,
  nonprofits, and other organizations, through the studio.

If I'm not the right fit for what you need, I'll say so. That has cost me work and
kept me clients for a decade.

📧 erik@ascentwebs.com · 🔗 [LinkedIn](https://www.linkedin.com/in/erikbertrand/) ·
🌐 [ascentwebs.com/capabilities](https://ascentwebs.com/capabilities/) ·
📄 [Résumé](https://ascentwebs.com/erik-bertrand-resume.pdf)

---

## SyteCheck — the thing I'd point at first

[**sytecheck.app**](https://sytecheck.app) · Python · FastAPI · Celery · React ·
TypeScript · Postgres · Redis · Playwright · Docker

The tools that analyze a website properly are priced for enterprises and shaped for
marketers. The free one is a developer's utility with no accounts, no history, and no
report you'd put in front of a client. SyteCheck closes that gap: ten categories of
analysis against any URL — HTML validity, SEO, broken links, WCAG 2.2 AA
accessibility, performance, security headers, responsive layout, content freshness, AI
visibility, and a visual and aesthetic evaluation — returned as one scored report
written primarily for the site's owner rather than for a specialist. And the report
includes actionable recommendations to fix issues.

The visual category is the part nobody else ships: the page is rendered at three
viewport sizes, screenshotted, and scored against a structured rubric for typography,
whitespace, color, hierarchy, and how prominent the calls to action are.

Behind it is an async Celery worker pool doing the slow work over Postgres and Redis,
a FastAPI service with a public API — keys, webhooks, and rate limits — and a React
front end that uses that same API. Containerized and deployed behind Render, with the
SPA hosted at Cloudflare.

The code was the more straightforward half. The rest is what decides whether something
is a product or a demo: product requirements from a market and competitive analysis, a
thorough architecture design and a phased product development plan, a cost model
measured per scan, plan entitlements enforced at the chokepoints rather than merely
published, billing through a merchant of record so tax is handled everywhere it sells,
a retention policy a scheduled purge job actually carries out, and a tenant isolation
boundary pinned by a test suite that sweeps every route one tenant could use to reach
another's data.

One engineer, idea to deployed and monetized product. It's the clearest evidence I
have of what I can hold on my own.

---

## Enterprise engineering

Fifteen years at Dyn and Oracle Cloud, on an email delivery platform that grew past
**six billion messages a month**.

It was far more than a website: a console UI, a public API for automation, inbound and
outbound SMTP subsystems, caching layers, and the bounce, complaint, unsubscribe, and
engagement handling behind them. Hundreds of servers, over twenty hostclasses, millions
of lines of code, and a 99.9% uptime commitment.

I led the migration that moved that service — and several hundred customers — from
on-prem to cloud **with zero downtime**. Capacity planning, compute and storage
planning, data migration in flight, operations and feature parity, and a phased plan
that held while customers kept using the service throughout. Rebuilding an airplane
already in flight.

That work is where the discipline comes from, and I apply it to sites a thousand times
smaller: plan the migration, keep the links, test on the real thing, and never launch
on a Friday. Twenty-five years in, I've been the person who builds it, the person who
migrates it, and the person who gets called when it falls over at 2am. Full
accountability and attention, at every stage.

---

## Web work

I've kept an informal, side web practice for small businesses and nonprofits all along.
I've now formalized it with a solid brand, into a studio. This takes a back seat to
permanent and contract work, but allows me to help local businesses and organizations
with their needs; it's meaningful and fun work. SyteCheck, the SaaS product I developed,
came from this, and I'm using it to enhance my offerings. Several other outcomes to
highlight, rather than a list of deliverables:

| What changed | Detail |
|---|---|
| A statewide "buy local" nonprofit got a **1,000-page rebuild** | A searchable map and directory of 800+ members, each editing their own profile. WordPress, custom PHP, payments, member directory & e-commerce integration |
| A truck repair shop got off Magento | **1,000+ products and variations** migrated intact, onto a WooCommerce store the owners could actually run |
| A professional choir's hand-edited HTML became editable | **100+ pages** of inconsistent markup migrated into a CMS the staff could use |
| A community theater group's site got **400% faster** | Performance and visual design work, with Turnstile on the forms |
| A nonprofit ran for **ten years** on quiet upkeep | Continuous maintenance and content care, then a clean migration when it was time to hand it off |
| A streamlined email, calendar, and file system | Helped a thriving church migrate their staff to Google Workspace, retaining email/calendar history and all files they wanted to keep |
| Faster website with better uptime | Migrated the website for that same church to a different, more reliable ISP |

[ascentwebs.com](https://ascentwebs.com) is itself a working sample: Astro, static
output from Markdown files, plain CSS on brand tokens, **zero JavaScript bundle**, a
generated hash-based CSP, WCAG 2.2 AA verified (with [SyteCheck](https://sytecheck.app))
rather than assumed, and no third-party request on any page but the one that needs a
CAPTCHA. Deployed to Cloudflare Workers, and blazing fast.

---

## How I work with AI

I develop alongside AI daily — not as an experiment, and not as autocomplete. SyteCheck
and the studio site were both built this way, start to finish, and the approach is now
part of what I'm hired for.

What it looks like in practice:

- **Written conventions the model has to follow.** Each repo carries a `CLAUDE.md`
  covering architecture, voice, accessibility, motion, and security policy. Most of
  what makes AI-assisted work good or bad is decided *before* any code is generated.
- **Specification first, then code.** Requirements, architecture, and a plan, written
  down and argued with. The model is better at the second half than the first, and
  it's very willing to build the wrong thing quickly.
- **I'm the reviewer.** Generated code gets the same scrutiny as a colleague's pull
  request, plus a bias toward deleting it. A build passing is not the same as the code
  being correct.
- **Verification over vibes.** Typecheck, tests, and the real thing in a real browser.
  Contrast ratios computed, not eyeballed; measured values recorded in comments so the
  next person — or the next model — doesn't re-guess them.
- **Judgment stays mine.** What to build, what to refuse, what a client actually needs,
  and what happens to it in five years. Twenty-five years of experience, and some scar
  tissue along the way, is the part that doesn't come out of an AI model.

The honest summary: it makes this senior engineer considerably faster and even more
efficient, and scalable.

---

## Stack

**Languages & frameworks** — Python · TypeScript · React · JavaScript · PHP · Java ·
Node · SQL · SMTP

**Platforms & infrastructure** — Linux · Docker · AWS · OCI · Cloudflare · Render ·
Postgres · Redis · Git · CI/CD · Google Workspace · Claude Code

**Web & CMS** — WordPress · WooCommerce · Astro · Squarespace

**The work itself** — Full-stack applications · Website rebuilds · Platform migrations ·
Systems integration · Performance and Core Web Vitals · Accessibility (WCAG 2.2 AA) ·
Technical SEO · AI-assisted development

---

## Off the clock

- **All 115 of the Northeast's 4,000-foot peaks, hiked in winter.** It took
  considerably longer than any website I've built. The mountains in my logo aren't
  just decoration.
- **I sing in choirs**, which is how a fair number of my side projects came to exist.
  I'm a regular soloist and cantor as well.
- A native New Englander — New Hampshire born, Cape Cod based — and reliably happier
  outdoors than in.
- Traveler and Adventurer - valuing experiences rather than things, taking in
  varied architecture and cultures internationally and domestically
- Volunteer - helping my local church, have served on multiple non-profit boards, and
  do occasional work for Habitat for Humanity

---

<sub>Cape Cod, Massachusetts · Remote, US Eastern · erik@bertpc.com</sub>
