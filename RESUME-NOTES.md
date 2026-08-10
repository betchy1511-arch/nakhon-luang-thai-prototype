# RESUME — Nakhon Luang Thai Homepage Prototype

## LATEST — menu navigation pass, 2026-08-10 (read this first)

Beth reviewed `?v=3&m=1` and flagged three things, all now fixed, pushed and verified live at commit `3c2e5c8`. She is checking the result on 2026-08-11.

1. **Hero subhead contradicted the order-online pitch.** "made to order, ready when you get here" now reads "Real regional Thai cooking, ordered online and cooked fresh for pickup". Pickup is correct: the storefront is **pickup only, no delivery**.
2. **Category tiles went nowhere.** All 9 tiles pointed at the generic `/order/`. They now deep-link to the ordering storefront's own category anchors.
3. **Only 6 of 15 categories were shown.** Beth listed the missing ones (sides, fried rice, soup, hot AND cold drinks, kid's menu, dessert, entree). The row now renders **all 15**, in the storefront's order, using the storefront's own names. She explicitly asked for **Entree**, not "Stir-Fry".

Also corrected while verifying: **3 of 4 popular-dish prices were invented** (Khao Soi $16 to $17, Pad Kra Pao $14 to $22.95, duck Drunken Noodles $18 to $24.95).

**Key technical fact:** `/order/` is only an `.olo-embed` iframe wrapper around `https://ezoo.app/nakhon-luang`. Its `embed.js` builds the iframe src from `data-src` and **never reads `location.hash`**, so `/order/#cat-X` cannot deep-link. Links therefore go direct to `ezoo.app#cat-XXX`. The durable fix, if links should stay on the client domain, is to make that plugin forward the hash.

**The full category map, counts, dish-to-category mapping and the counting traps are in memory `nakhon-luang-thai/project_nlt_homepage_prototype_aug2026.md`.** Read it before touching menu links again.

**Still open:** the `Ready in ~20 min` pill is unverified copy with no source; V1 deliberately still shows a 3-chip teaser rather than all 15.

---

**Status when paused:** v1 shipped to GitHub Pages. Beth pushed back that it stripped too much live-site content. Rebuild scoped but NOT started.

**Live URL (v1, current):** https://betchy1511-arch.github.io/nakhon-luang-thai-prototype/
**Repo:** https://github.com/betchy1511-arch/nakhon-luang-thai-prototype
**Local:** `C:\ClientWork\Magister\Nakhon Luang Thai\prototype\index.html`

## What's already true in v1
- 3 variants behind PICKER.md chrome (Split Hero / Editorial + Dock / Kitchen)
- Cream + amber palette, Fraunces + Inter typography
- Order Online as dominant CTA on every variant
- Phone demoted to footer, mobile sticky Order bar on all three
- Real Colorado Springs / Rockrimmon content, real dishes, real hours
- Zero external image deps (SVG silhouettes + gradients)

## Beth's push-back (2026-08-10)
> "ok we said we need to focus on online ordering but didnt say remove all the items from the live site"

The v1 prototypes flipped the CTA hierarchy correctly but compressed brand story too aggressively. Fix = re-add every section the live site has, keep Order Online as the dominant CTA at every scroll break.

## Live-site full section inventory (fetched 2026-08-10)

**Top nav (currently on live site):** Home · Menu · About · Contact · Reservations · Order

**Homepage sections in order:**

1. **HERO** — heading "Authentic Thai Cuisine · Colorado Springs, CO", body "Regional Thai cuisine with bold, balanced flavors, now open in Rockrimmon." CTAs: Order Online, Reserve a Table, View the full menu.
2. **PHILOSOPHY** — "Bold flavors. Refined craft." Copy: "Nakhon Luang Thai Kitchen offers a modern, welcoming approach to traditional Thai cuisine. Rooted in the backgrounds of our founders and inspired by Bangkok and regional Thai influences, our kitchen is guided by care, balance, and respect for tradition. The result is a dining experience that feels thoughtful, cultural, and inviting, a place to enjoy Thai food made with purpose." Image: Pad kra pao.
3. **STORY / Flavors of the region** — copy: "Our menu highlights classic Thai dishes shaped by regional traditions from Bangkok, Isan, Northern and Southern Thailand, and Lao cuisine. Guests will find familiar favorites alongside regional influences, from aromatic curries and stir-fried dishes to timeless noodle plates. Each dish is prepared with fresh ingredients and a careful balance of flavor, comforting, authentic, and satisfying." CTA: Full Menu. Image: Nakhon Luang table spread.
4. **FEATURED DISHES** — 3 cards with verbatim descriptions:
   - **Khao Soi** — "Northern Thai coconut curry soup with egg noodles, braised chicken, crispy noodles, shallots & lime."
   - **Pad Kra Pao** — "Stir-fried Thai holy basil with bell peppers, onions & chili, topped with a fried egg."
   - **Drunken Noodles** — "Wide rice noodles stir-fried with crispy duck, Thai basil, bell peppers, onions & chili."
5. **EXPERIENCE / Gather. Sip. Savor.** — copy: "Enjoy a relaxed, welcoming atmosphere where authentic Thai cuisine meets elevated drinks. Whether you're gathering with friends or enjoying a casual night out, our curated wine list, handcrafted cocktails, rotating craft beers, and genuine hospitality make every visit feel special." CTA: Make a Reservation. **THIS SECTION WAS OMITTED FROM V1 — needs to come back.**
6. **HOURS & CONTACT CALLOUT** — "11 to 8:30 Open Daily · Lunch & Dinner" · (719) 531-5175 "For Reservations"
7. **RESERVATIONS CTA** — "Reserve Your Table Tonight" · "Reservations recommended. Walk-ins welcome. **Private events available.**" CTAs: Order Online, Make a Reservation. **Private events line was omitted.**
8. **FOOTER** — Logo, tagline, copyright.

## Em-dash locations to fix in current index.html
Found via `Grep --` on the file:
- Line 6: `<title>Nakhon Luang Thai Kitchen — Homepage Prototype</title>`
- Line 958: JS comment `// ============ Variant 1 — SPLIT HERO ============` (comment, low priority but fix)
- Line 981: `<em>Khao Soi Gai — Northern Thai coconut curry</em>` (V1 hero caption)
- Line 1047: `<h2>Regional Thai cooking — Bangkok, Isan, the North, the South, and Lao.</h2>` (V1 story)
- Line 1091: JS comment `// ============ Variant 2 — EDITORIAL + DOCK ============`
- Line 1149: `<h3>Come find us — or order in.</h3>` (V2 visit)
- Line 1197: JS comment `// ============ Variant 3 — KITCHEN (order-dominant) ============`

Replace all with commas/periods per Beth's universal em-dash rule.

## Rebuild plan per variant (approved axes, don't re-brainstorm)

### V1 SPLIT HERO — add these BELOW the existing hero
1. Philosophy section: "Bold flavors. Refined craft." centered, with dish icon aside
2. Featured Dishes: 3-card horizontal strip using live-site verbatim descriptions
3. Story: "Flavors of the region" left-aligned with visual right
4. Experience: "Gather. Sip. Savor." dark card with beverage list, Reserve CTA
5. Reservations: "Reserve Your Table Tonight" + private events line + Order Online + Reserve buttons
6. Keep existing Visit + Footer

### V2 EDITORIAL + DOCK — enrich existing sections
1. Add Philosophy full paragraph before Story (currently only has short story blurb)
2. Update dish descriptions to verbatim live-site copy
3. Add Experience section (missing entirely) between Dishes and Visit
4. Add Reservations CTA block before footer, with private events line

### V3 KITCHEN — add compressed content-strip below Popular grid
1. Keep hero + category grid + popular (v3's soul is compressed brand)
2. Add 2-column content strip: LEFT = Philosophy + Story combined, RIGHT = Experience card
3. Add Reservations CTA strip with private events line
4. Keep Visit + Footer

**Divergence preserved:** V1 flows narratively, V2 is fully editorial, V3 keeps ordering-first hero + compact-below.

## What's NOT decided yet
- Which of the 3 variants Beth prefers (recommendation in v1 was Split Hero)
- Whether to loop in Wendy / Dimitri before or after her pick
- Menu page prototype (next run, separately)
- WP Engine dev upload plan (post-pick)

## When resuming, run in this order
1. Read this file
2. Read `C:\ClientWork\Magister\Nakhon Luang Thai\prototype\index.html` (context refresh)
3. Rewrite index.html with additions above + em-dash fixes
4. `git add . && git commit -m "..." && git push`
5. Poll for Pages rebuild (~30s)
6. Verify all 3 variants render, all new sections present via curl content check
7. Report to Beth
