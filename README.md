# ProdPack site (prodpack.dev)

The marketing site for ProdPack. Static, multi-page, no build step. Open
`index.html` directly, or point `prodpack.dev` at this folder.

## Pages

- `index.html` — Home (simple overview: hero, the idea, three teasers, tech, pricing teaser)
- `how-it-works.html` — the wizard walked step by step with real app screenshots
- `modules.html` — the module catalog and the generated architecture
- `security.html` — security-first: secrets at bootstrap, the measures, AI security review
- `pricing.html` — invitation-only closed paid beta terms
- `legal.html` and `legal/` — pre-order policy index and synchronized policy copies

## Assets

- `shots/` — real ProdPack screenshots (captured from the running app)
- `icons/` — SVG icon components used by the module catalog

## Story / messaging

Pick feature packs, ProdPack composes them into one secured repository, validates
the plan, and boots a verified golden path locally. Selected Docker, CI, and
provider release files make the repository deploy-ready, but buyers provision
accounts, credentials, DNS, and the production rollout. Generated outputs carry
broad perpetual commercial rights with no ProdPack runtime tie, subject to the
published output and third-party terms.

## Notes before paid orders

- Public pricing is intentionally withheld during the invitation-only pilot.
  Each approved order must state seller identity, price, seats, purchase date,
  supported systems, and the 12-month update window.
- Application links use `support@prodpack.dev`. Confirm the mailbox, counsel-
  approved terms, payment flow, and private signed-DMG delivery before taking
  money.
- Run `bun run check:landing` whenever policies or claims change so synchronized
  legal copies, links, and prohibited placeholder claims stay checked.
- The technology-icon strip on the Home page loads from `cdn.simpleicons.org`
  (external, like the Google Fonts link). Inline the SVGs for a self-contained
  site.

## Conventions

Light Atelier theme, the app logo, Hanken Grotesk + Instrument Serif + JetBrains
Mono. No em/en dashes, no emoji (SVG icons instead). Reveal animations are gated
behind an `html.js` class so content shows with JS off; `prefers-reduced-motion`
honored. Responsive with no horizontal overflow at 390px.
