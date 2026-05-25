# Studio PRA demo: Krug + Impeccable review

## Verdict

PASS WITH FIXES applied.

## Mode

Existing Design Review.

## Skill lens

- `krug-ux-audit`: reduce cognitive friction, clarify first step, distinguish paths/desks/services.
- `impeccable`: keep the premium Studio PRA identity, avoid generic redesign, preserve refined red/gold accents and strong legal presence.

## Top cognitive frictions found

1. The distinction between `Desk`, two legal paths and three service desks required too much interpretation.
2. The primary next step competed with multiple contact CTAs: `Write us`, `Request a first assessment`, email badge, final contact CTA.
3. The multilingual structure was brand-appropriate, but the user needed clearer signposts for where to start.

## Changes applied

### Hero and navigation

- Changed navigation label from `Desk` to `Legal paths`.
- Changed secondary hero CTA from `Find the right desk` to `Choose your legal path`.
- Rewrote the hero lead to explicitly name the two audiences:
  - DACH clients needing Italian-law assistance.
  - Italian clients needing coordinated support abroad.
- Changed the side-panel email CTA from the bare email address to `Email the international desk`.

### Pathways section

- Reframed the section from generic legal paths to client paths.
- Added a stronger instruction: choose based on country/language starting point.
- Added visible badges on the two cards:
  - `Parto da Germania, Austria o Svizzera`
  - `Parto dall'Italia`

### Services section

- Reframed the services as the step after choosing the path.
- Added a small explanatory note: choose path first, then scan service desk.
- Added labels to the service cards:
  - `Cross-border matters`
  - `Clienti italiani`
  - `Deutschsprachige Mandanten`

## Desktop QA

- No obvious overflow or broken layout detected.
- Hierarchy remains strong.
- The page now communicates the choice model more clearly: hero -> legal path -> service desk -> offices/contact.
- Remaining minor risk: hero is still visually dense, but acceptable for the premium legal identity.

## Mobile QA

Screenshot: `qa/mobile-home.png`

- No horizontal overflow visible at 390px.
- CTA buttons remain visible and tappable.
- Hero headline is very large but not cut off.
- Contact bar is tall, but still readable.
- Mobile nav hides secondary links, but the hero CTA `Choose your legal path` keeps the main next step available.

## Suggested next tests

1. 5-second test: ask a user what Studio PRA does and where they would click first.
2. First-click test: `Sono un cliente tedesco con una questione legale in Italia: dove clicco?`
3. First-click test: `Sono un cliente italiano con un problema in Germania: dove clicco?`

## Files changed

- `index.html`
- `KRUG_IMPECCABLE_REVIEW.md`
- `qa/desktop-home.png`
- `qa/mobile-home.png`
