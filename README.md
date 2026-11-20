# Erik Bertrand

Full-stack software engineer based in the northeast USA. Twenty-plus years building for
the web, fifteen of them in enterprise engineering at Dyn and Oracle. I now run
[Ascent Web Solutions](https://ascentwebs.com), a boutique web studio, and built
and released [SyteCheck](https://sytecheck.app), an online service of my own that
checks websites for accessibility, security, performance, and more.

I write Python, TypeScript, React, and PHP, work in Linux and cloud infrastructure, and
I focus especially on customer experience, a thoughtful development process, test
coverage, and well-documented architecture and runbooks. I care more about what a
system looks like in five years than what it looks like on launch day.

**Currently open to:** permanent roles, contract engineering engagements, and website
projects for businesses and organizations.

---

## What I'm looking for

Three separate things, and I'm happy with any of them.

- **Permanent roles.** Full-stack, web developer, and front-end work, at whatever
  level fits. Remote, or hybrid within reach of Cape Cod in Massachusetts.
- **Contract engineering.** Full-stack/web/front-end roles, agency overflow,
  fixed-scope builds, migrations, and integration work. Remote, US Eastern,
  used to being an engineer on a distributed team.
- **Website projects.** Fixes, refreshes, rebuilds, and ongoing care for small
  businesses, nonprofits, and other organizations, through the studio.

If I'm not the right fit for what you need, I'll say so and help put you in contact with
someone who can.

📧 erik@bertpc.com · 🔗 [LinkedIn](https://www.linkedin.com/in/erikbertrand/) ·
🌐 [ascentwebs.com/capabilities](https://ascentwebs.com/capabilities/) ·
📄 [Résumé](https://ascentwebs.com/erik-bertrand-resume.pdf)

---

## Full-stack engineering

I work across the whole stack: Python and FastAPI services, async workers, Postgres
and Redis, React and TypeScript front ends, and the CI/CD and deployment underneath.
Two bodies of work show it best: a product I built on my own, and fifteen years on a
platform that couldn't go down.

### SyteCheck: the thing I'd point at first

[**sytecheck.app**](https://sytecheck.app) · Python · FastAPI · Celery · React ·
TypeScript · Postgres · Redis · Playwright · Docker

The tools that analyze a website properly are priced for enterprises and shaped for
marketers. The free one is a developer's utility with limited scope, no history, and no
report you'd put in front of a client. SyteCheck closes that gap: ten categories of
analysis against any URL (HTML validity, SEO, broken links, WCAG 2.2 AA
accessibility, performance, security headers, responsive layout, content freshness, AI
visibility, and a visual and aesthetic evaluation), returned as one scored report
written primarily for the site's owner rather than for a specialist. And the report
includes actionable recommendations to fix issues.

The visual category is the part nobody else ships: the page is rendered at three
viewport sizes, screenshotted, and scored by Claude against a structured rubric for
typography, whitespace, color, hierarchy, and how prominent the calls to action are.

Behind it is an async Celery worker pool doing the slow work over Postgres and Redis,
a FastAPI service with a public API (keys, webhooks, and rate limits), and a React
front end that uses that same API. Containerized, and deployed on Render, Cloudflare
Pages, and R2.

It's tested and deployed the way a larger team would do it: roughly 1,600 backend tests, a pull-request
gate, a nightly run of the full suite against the real Docker images plus Playwright
end-to-end tests, a daily canary scan through the production API, and a deploy
pipeline that won't let new code reach a database that hasn't been migrated. The
public API comes with an OpenAPI spec, signed webhooks, and example clients in five
languages. The UI and reports render in 12 languages. Sentry, cron heartbeats, and an
admin system page watch production, and automated follow-up emails and
per-prospect offer codes help support user base growth.

In a way, the code was the more straightforward half. The rest is dedicated to treating
all this as a real product, not a demo:
- product requirements from a market and competitive analysis
- a thorough architecture design and a phased product development plan
- a cost model measured per scan
- plan limits the code actually enforces, not just ones listed on the pricing page
- billing through a merchant of record so tax is handled everywhere it sells
- a retention policy a scheduled purge job actually carries out
- a tenant isolation boundary pinned by a test suite that sweeps every route one tenant could use to reach
another's data

All this from one engineer, from idea to full-featured, secure, scalable product deployed in
production, with billing live. It's the clearest evidence I have of what I can hold on my own.

### Enterprise engineering

I spent fifteen years at Dyn and Oracle Cloud as a founding member and lead on an email
delivery platform that grew past **six billion messages a month**, and created the cloud-native
version of that service.

It was far more than a website or basic app: a console UI, a public API for automation, inbound and
outbound SMTP subsystems, caching layers, and the bounce, complaint, unsubscribe, and
engagement subsystems behind them. Hundreds of servers, over twenty hostclasses, millions
of lines of code, several database clusters, and a 99.9% uptime commitment.

I led the migration that moved that service, and several hundred customers, from
on-prem to cloud **with zero downtime**, realizing **40% lower infrastructure cost**.
Capacity planning, compute and storage planning, data migration in flight, operations and
feature parity, and a phased plan that held while customers kept using the service
throughout. It was like rebuilding an airplane already in flight.

I also led a CI/CD overhaul for a team of 30 engineers: nightly integration builds
that surface problems well before release, better pull requests, and production
deployment prep cut by about 60%, from a day or two to a few hours.

That work is where the discipline comes from, and it shows up in everything I build
now. SyteCheck's tenant-isolation tests, daily canary scan, CI gates, ongoing test
coverage, and migration-first deploys are habits from running a service people
depended on around the clock. On client sites a thousand times smaller, it means
planning the migration, keeping the links, testing on the real thing, and never
launching on a Friday. Twenty-five years in, I've been the person who builds it,
the person who migrates it, and the person who gets called when
it falls over at 2am. Being the one on call when production breaks is what shapes
how I build and migrate systems.

---

## How I work with AI

I develop alongside AI daily, not as an experiment and not as autocomplete. SyteCheck
and my web studio site were both built this way, start to finish. I also build AI into
products and automate my own business workflows with it, and enjoy bringing this
experience to an employer or customer to help them succeed.

What it looks like in practice:

- **Written conventions the model has to follow.** Each project repo carries a
  `CLAUDE.md` (linked as `AGENTS.md`, so other agents read the same rules) covering
  architecture, voice, accessibility, motion, and security policy. The larger ones
  work as a map: the rules that apply to every session up front, then an index of
  invariants that are easy to break, each pointing to the doc that records what was
  measured and what has already been tried and failed. Most of what makes AI-assisted
  work good or bad is decided *before* any code is generated.
- **Context about me, too.** The same files say what I know deeply and what I'm still
  learning, so in newer territory the model explains its trade-offs instead of quietly
  picking one.
- **Specification first, then code.** Requirements, architecture, and a plan, written
  down and argued with. The model tends to be better at code than specification;
  it's very willing to build the wrong thing quickly, without detailed guidance.
- **I'm the reviewer.** Generated code gets the same scrutiny as a colleague's pull
  request, plus a bias toward deleting or redoing it. A build passing is not the same
  as the code being correct.
- **Verification over vibes.** Typecheck, tests, and the real thing in a real browser.
  Contrast ratios computed, not eyeballed; measured values recorded in comments so the
  next person, or the next model, doesn't re-guess them.
- **Judgment stays mine.** What to build, what to refuse, what a client actually needs,
  and what happens to it in five years. I leverage my twenty-plus years of experience,
  with the occasional scar tissue gained along the way, to keep the model on the right
  track.

### AI in the product

- **Claude features in SyteCheck:** the visual design critique (screenshots scored
  against a structured rubric), a plain-English executive summary with the top
  recommended actions, and on-demand translation of reports into 12 languages, cached
  so each translation is paid for once. Every call records its token cost, so AI spend
  per scan was measured before pricing was set. If an AI call fails, the report still
  completes without it.
- **[sytecheck-mcp](https://github.com/BertPC/sytecheck-mcp):** a published MCP server
  (npm and the official MCP registry) that lets Claude, Cursor, and other agents run
  audits and read reports. It's built so an agent can't run up a bill by accident: the
  one tool that spends quota asks before it runs, and read-only API keys can't start
  scans at all.

### Workflows I've automated

I package repeatable work as Claude skills: written procedures with their own scripts,
reference files, and permissions.

- **Website assessment:** turns a URL into a branded 12–16 page PDF for a prospect. It
  crawls the site's structure, runs a full SyteCheck scan, checks the platform, domain,
  and email DNS, captures phone, tablet, and desktop screenshots, compares the content
  against what that kind of business needs, and closes with three priced options. The
  same skill writes care plan proposals.
- **Local prospecting:** finds and vets Cape Cod businesses in an industry, scans their
  sites, picks the right kind of email by a written rubric, and puts the drafts in a
  local review app beside the live site and the scan findings. Approved drafts go to
  my mailbox for me to tailor and send.
- **Agency prospecting:** finds and scores smaller web and marketing agencies who
  might find SyteCheck useful, drafts peer-to-peer outreach with a unique offer code
  for each, and keeps a lead log with follow-up dates and a weekly funnel report.
- **Job search:** screens about ten job sources against my own criteria, scores each
  match, and logs it in a tracker page I built. A companion skill tailors a resume for
  each posting using only facts on record that I wrote, then checks the rendered page layout.

They share a few rules: one source-of-truth file each workflow must read first, every
claim traceable to a source, tools limited to a handful of fixed scripts, no secrets on
a command line, polite request rates on other people's sites, and drafts only. Nothing
is sent without my review.

In short: it makes me considerably faster, but the hard parts of the job still take
experience and judgment.

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
| The same church's site, kept current | Accessibility fixes from axe audits, PHP 8.5 compatibility repairs during a server upgrade, and a tighter Content Security Policy |
| A gym and smoothie bar got **one number to call** | Website content and new features, WordPress upkeep, social integrations, and basic IT support, until the business was sold |
| A volunteer choir ran its own site for **about 15 years** | The smallest site that met the need, set up so a non-technical volunteer could update it |

For ongoing upkeep, the studio offers [three care plans](https://ascentwebs.com/care-plans/),
and a new conversation can start with a free written assessment of the current site.

[ascentwebs.com](https://ascentwebs.com) is itself a working sample: Astro, static
output from Markdown files, plain CSS on brand tokens, **zero JavaScript bundle**, a
generated hash-based CSP, WCAG 2.2 AA verified (with [SyteCheck](https://sytecheck.app))
rather than assumed, and no third-party request on any page but the one that needs a
CAPTCHA. Deployed to Cloudflare Workers, and blazing fast.

---

## Stack

**Languages & frameworks:** Python · TypeScript · React · JavaScript · PHP · SQL ·
FastAPI · Celery · Tailwind · SMTP

**Working knowledge:** Node · Java

**Platforms & infrastructure:** Linux · Docker · AWS · OCI · Cloudflare · Render ·
Postgres · Redis · Git · GitHub Actions · CI/CD · Sentry · Google Workspace

**Testing:** pytest · Playwright · Vitest

**AI:** Claude Code · Claude API · MCP

**Web & CMS:** WordPress · WooCommerce · Astro · Squarespace

**The work itself:** Full-stack applications · Website rebuilds · Platform migrations ·
Systems integration · Performance and Core Web Vitals · Accessibility (WCAG 2.2 AA) ·
Technical SEO · AI-assisted development

---

## Off the clock

- **All 115 of the Northeast's 4,000-foot peaks, hiked in winter.** It took
  considerably longer than any website I've built. That's where the mountains
  in my logo come from.
- **The Trailwrights 72, finished in 2026:** all 72 of New Hampshire's 4,000-foot
  peaks, each on a separate hike, plus 72 hours of trail work. I volunteer as an AMC trail adopter, too.
- **I sing in choirs** and with the Sky Meadow Recorder Consort, which is how a fair
  number of my side projects came to exist. I'm a regular soloist and cantor as well.
- A native New Englander, New Hampshire born and Cape Cod based, and reliably
  happier outdoors than in.
- **A traveler at heart.** I'd rather collect experiences than things, especially
  architecture and culture, here and abroad.
- **A volunteer.** I help at my local church, have served on multiple nonprofit
  boards, and do occasional work for Habitat for Humanity.

---

<sub>Cape Cod, Massachusetts · Remote, US Eastern · erik@bertpc.com</sub>
