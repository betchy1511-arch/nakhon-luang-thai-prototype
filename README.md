# Nakhon Luang Thai Kitchen — Homepage Prototype

Three divergent homepage redesigns for **nakhonluangthaicos.com** (Colorado Springs, CO) behind a picker. Client: **Magister Digital pilot** — earn $1 per online order, path to ~1,000-location rollout.

## View live

Deployed to GitHub Pages — flip through variants with the picker at the top of the screen.

**Keys:** `1` `2` `3` switch variants · `←` `→` cycle · `R` replays motion

Deep-link a specific variant with `?v=2` or `?v=3`.

## The three variants

All three share: cream + amber palette, real Colorado Springs content, phone number demoted to footer, mobile sticky Order bar, Fraunces + Inter typography.

| # | Name | Axis | When to ship it |
|---|---|---|---|
| 1 | **Split Hero** | Order and brand get equal real estate. Left = atmospheric hero, right = a live ordering panel (category shortcuts + Popular Now list + big Order CTA). | Best pilot-safe bet. Story survives, ordering wins the first click. |
| 2 | **Editorial + Dock** | Brand-first cinematic hero. Ordering becomes inescapable via a persistent gold-bordered dock at the bottom of every screen. | Highest brand approval. Slower to first click. |
| 3 | **Kitchen (Order-Dominant)** | The homepage IS the ordering funnel. Hero is a 6-cell category grid; brand story compressed to a strip. Sweetgreen / Cava vibe. | Highest conversion ceiling. Chef-owner may push back on the aesthetic. |

## Brief (from Brian)

- **Primary objective:** flip site from phone-first to online-order-first
- **Copy incentives:** *Skip the line* · *No wait* · *More convenient*
- **Sticky Order Online buttons throughout**
- **Menu page = next highest-intent surface** (queued as next prototype run)
- **Deploy target:** WP Engine dev environment after variant sign-off
- **SEO campaign** launches immediately after design approval — Map Pack, organic, AI Overviews, ChatGPT/LLM, on-page, technical, content
- **Collaboration:** Wendy at Magister, Dimitri as needed

## Success metrics

- Minimum: 1,000 online orders / month
- Ideal: 1,500 online orders / month

## Stack (prototype)

Single self-contained `index.html`. No build step. No external image dependencies (SVG dish silhouettes on gradient backgrounds). Google Fonts (Fraunces + Inter) with system fallbacks. Fully responsive down to 375px.

## Once a variant is picked

The winning direction converts to a WP theme/template and gets pushed to WP Engine dev per the brief. Menu page runs next as its own prototype pass — that page carries the highest ordering intent and warrants its own divergence exploration.
