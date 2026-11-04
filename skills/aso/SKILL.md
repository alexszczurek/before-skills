---
name: aso
description: Write, audit, or improve an iOS App Store listing — app name, subtitle, keyword field, screenshots, app icon, preview video, creative assets, tags, ratings strategy, localization, and featuring nominations. Use when creating or reviewing App Store metadata, doing keyword research, planning a metadata update, or when the user mentions ASO, App Store Optimization, app store listing, keywords, subtitle, screenshot captions, preview video, app icon, Liquid Glass, creative assets, product page header, search results creative, Asset Library, featuring, ratings prompt, Apple Ads, screenshot rejection, Guideline 2.3.3, screenshot sizes, or iPhone Duo.
---

# App Store Optimization

You are optimizing an iOS App Store listing. 70% of App Store visitors find apps through search and 65% of downloads happen immediately after a search — the listing does more selling than the landing page. Every rule below exists because the search algorithm indexes a small, known set of surfaces, and everything else is a conversion tool, not a discovery tool.

## The only fields that rank

Apple indexes exactly 160 characters of owned keyword surface. Never spend effort "optimizing the description for keywords" — the description and promotional text (170 chars, updatable without a new version) are NOT indexed. They affect conversion, not discovery. The description still matters for one discovery mechanism: Apple's LLM generates App Store *tags* from the description and screenshots, so it must name the app's category and core use cases in plain words — for the tag generator, not for keyword rankings. Google also indexes the description on the web App Store (apps.apple.com), a second discovery channel Apple's own search ignores.

| Field | Limit | Keyword weight | Visible to users |
|---|---|---|---|
| App Name | 30 chars | Highest | Yes |
| Subtitle | 30 chars | Second | Yes |
| Keyword Field | 100 chars | Third | No |

Also indexed: category, screenshot content (Apple-confirmed at WWDC25 — extracted by AI analysis, not OCR), tags, and in-app event names (as reinforcement of existing keywords, see In-app events).

Beyond text, Apple confirms downloads and ratings as ranking inputs (plus an unspecified "and more"). Retention and uninstall-rate demotion is officially documented only on Google Play, not iOS — treat it as likely, not confirmed. Either way, low retention starves download velocity, so the practical rule holds: ASO cannot fix a leaky product.

**The zero-overlap rule:** never repeat a word across the name, subtitle, or keyword field. Apple combines tokens across all fields, so a duplicated word is a wasted slot that could have covered a new search query. When auditing a listing, check this first — it is the most common and cheapest-to-fix error.

## Ranking and conversion are separate jobs

Every surface serves ranking (being found), conversion (being tapped and installed), or both. Optimizing the whole listing in one undifferentiated pass silently trades one against the other — the classic failure is packing keywords into a subtitle or screenshot caption, gaining rank and losing installs.

| Surface | Ranking | Conversion |
|---|---|---|
| Keyword field | Yes | None — invisible to users |
| App name | Highest weight | Yes |
| Subtitle | Second weight | Yes |
| Screenshots | Yes (AI-analyzed) | Primary driver |
| Icon | None | Yes |
| Preview video | None | Yes |
| Product page header | None | Yes |
| Search results creative | None | Yes |
| Ratings | Yes | Yes |

Rules that follow from this split:

- **Diagnose before optimizing.** Low impressions = a ranking problem; high impressions with low conversion = a conversion problem. Never accept "optimize my listing" as one undifferentiated task — establish which axis is broken, and say so before changing anything.
- **Spend pure-ranking effort in the keyword field first.** It is invisible, so it cannot cost conversion. Fill all 100 characters before pushing any keyword into a user-visible field.
- **On dual-purpose surfaces (name, subtitle, screenshots), readability wins ties.** These are read by a human deciding whether to tap, and semantic search now penalizes stuffing directly — so a ranking gain bought with awkward copy loses twice.
- **Name the trade.** When a change helps one axis and risks the other, state the cost instead of presenting the change as a pure win.

## Think in intent clusters, not keywords

Apple's search increasingly interprets the semantic intent behind a query instead of matching literal tokens — it evaluates whether an app *satisfies* the query, and can rank you for terms you never targeted. Keyword-stuffed metadata now loses to natural-language metadata that clearly states what the app does. Consequences:

- Group keyword candidates into intent clusters (what the user is trying to accomplish) and make metadata answer the intent in plain language, not enumerate tokens.
- Prefer long-tail, high-intent queries over head terms: "remove background from photo" converts better than "photo editor" because the searcher already knows what they need — and head terms are also losing traffic to AI assistants (users ask ChatGPT or Gemini for app recommendations before ever opening the store), while in-store long-tail holds its value.
- Rich structured signals (in-app events, ratings) feed semantic ranking — they are not just conversion decoration.

## App Name

Formula: `Brand — Primary Keyword` or `Brand: Keyword Phrase`.

- Always use all 30 characters. Every unused character is keyword real estate thrown away.
- Put the single highest-value keyword in the name — it carries the highest ranking weight of any placement.
- Never use only the brand name unless the brand already has search volume. If nobody knows the name, nobody searches for it, and the app is banking entirely on browse traffic and press.
- Never include "app", "the", "free", or "best". Apple indexes common terms automatically; these eat character budget and add nothing.

Reference pattern: "Gentler Streak Workout Tracker" — the brand IS the keyword phrase. "Arc Search — Find it, Faster" — brand + primary keyword + value prop in one line.

## Subtitle

The subtitle is coverage expansion, not a tagline. It appears directly under the name in search results, so it must do two jobs at once: rank for new terms and read naturally at a glance.

- Never duplicate any word from the App Name (zero-overlap rule).
- Cover adjacent search territory the name doesn't: if the name handles "workout tracker", the subtitle covers "Health, Steps & Recovery".
- Use `&` and `,` to pack more terms into 30 characters.
- It must read as a sentence fragment a human would write. A keyword-stuffed subtitle tanks tap-through rate because users see it before they tap — a ranking gain that kills conversion is a net loss, and semantic search now penalizes stuffing directly.

## Keyword Field

Invisible to users; exists solely for the algorithm. Formatting rules are absolute:

- Comma-separated, NO spaces after commas — spaces consume characters that could hold keywords.
- Singular forms only — Apple auto-matches plurals, so "timer" covers "timers" and the plural form is pure waste.
- Never repeat any word from the name or subtitle.
- Never include the app name, developer name, or category name — Apple indexes these automatically.
- Fill all 100 characters. Count them. Under 95 used = the field is not done.
- Never include trademarked terms or competitor brand names — App Store Review Guideline 2.3.7 prohibits them and metadata rejections delay every release. Target competitor *keywords* (the terms they rank for), not their names.

What belongs here: synonyms of main keywords, common misspellings, long-tail variations, translated terms from secondary locales, competitor keywords (not names).

Example for "Deepwork — Focus Timer" / "Pomodoro & Concentration":
```
study,productivity,flow,block,distraction,adhd,work,session,interval,music,noise,task,habit,routine
```

## Keyword research procedure

Walk these steps in order — never skip to writing metadata from intuition:

1. **Brainstorm** every term a user might type: verbs ("meditate", "focus", "track"), nouns ("timer", "planner", "journal"), and problems ("can't sleep", "stress").
2. **Check App Store autocomplete** on a real device — the suggestions are actual user searches, the cheapest ground truth available.
3. **Extract competitor keywords** from the top 5–10 apps in the space (titles, subtitles; a tool like Astro or App Radar shows what they rank for).
4. **Score each candidate** on three axes: volume (are people searching it), relevance (does it genuinely describe the app), difficulty (is top 10 realistic). Target: medium volume + high relevance + low competition. "Photo editor" is owned by giants; "vintage film camera" might not be.
5. **Cluster by intent**: group survivors by what the searcher is trying to accomplish. Each cluster gets one coherent home (name, subtitle, a CPP, or the keyword field) — metadata that answers one intent clearly outranks metadata that gestures at five.
6. **Distribute**: top keyword → name, complementary terms → subtitle, everything else → keyword field, zero overlap between fields.

Pick 15–20 keywords for the first update and hold 15–20 in reserve — underperformers get swapped after 4–8 weeks, and having a bench ready is what makes iteration actually happen.

## Screenshots

Screenshots are advertisements built on the real app. A bare UI capture with no caption undersells it — users scan captions at thumbnail size and never study the UI — but a set that is mostly marketing art gets rejected (see the App Review gate below). The winning layout is the same one that passes review: real UI from the current build, in or out of a device frame, under a short caption. Only 1–3 screenshots show in search results.

Every screenshot gets a bold text caption at the top. Apple confirmed screenshots affect discoverability — its AI analyzes screenshot content — but Apple explicitly warns against stuffing keywords into visual assets. So: captions describe real features in the language users actually search ("Remove backgrounds in one tap"), never a keyword list. Stuffed captions read as desperate at exactly the moment the user decides whether to tap.

Assign jobs by position (max 10 slots):

| Position | Job |
|---|---|
| 1 | Main benefit — the only one most users ever see |
| 2 | Differentiation from alternatives |
| 3 | Trust signal — award, press, user count ("Apple Watch App of the Year") |
| 4–6 | Core features solving real problems |
| 7–8 | Recent features — proof the app is alive |

These are jobs, not permission to go full marketing: a trust-signal slot that shows only an award badge and no app is a marketing screenshot, and it counts against the gate below.

### App Review gate: more than half must show the app in use

Guideline 2.3.3 says screenshots should show the app in use, not merely title art, a login page, or a splash screen. Apple's App Review Help page for 2.3.3 (linked from Apple's October 5, 2026 developer news) turns that into a count: App Review approves a submission only when **more than half** of the screenshots show the app in use. The guideline text itself did not change; the count is how App Review applies it. Exactly half fails.

The count runs **per device type and per localization**, never across the whole listing. Each iPhone set, iPad set, and iPhone Duo set is judged on its own, and so is every language's version of each set. A localized set that swaps real UI for translated marketing slides can fail on its own while the English set passes.

| Screenshots in the set | Minimum showing the app in use |
|---|---|
| 1 | 1 |
| 2 | 2 |
| 3 | 2 |
| 4 | 3 |
| 5 | 3 |
| 6 | 4 |
| 7 | 4 |
| 8 | 5 |
| 9 | 5 |
| 10 | 6 |

Formula: minimum in-use = ⌊n / 2⌋ + 1.

What counts as "in use", from Apple's Help page:

- Real interface from the current build, showing what the app does. Captions, backgrounds, device frames, and overlays that demonstrate input (a touch point, Apple Pencil) are fine.
- Overlays and marketing visuals must not crowd out the app or hide its primary functionality. A tiny phone mockup behind a giant headline is marketing, not in use.
- Never in use: hardware or an overlay with no app interface behind it, title art, login pages, splash screens.
- One image of the app in use may span several screenshots (a panorama). Apple does not say how each slot of a panorama is counted, so count a slot as in use only when that slot on its own shows a meaningful part of real UI.

**Run this check before handing over any screenshot plan or design**, and run it again after every localization or device adaptation:

1. List every set: each device type × each localization.
2. Label every slot in every set: `in use` or `marketing`. When unsure, label it `marketing`.
3. For each set, compare the in-use count with the table. Report each set as `pass` or `fail`, with the count (for example "iPhone, de-DE: 3 of 6 in use — fail, needs 4").
4. Fix failures by turning marketing slots into captioned real UI, or by dropping marketing slots. Adding a marketing slot to a passing set can break it: 4 of 6 passes, 4 of 8 fails.

Only marketing slots are free. Benefit claims, trust signals, and feature summaries can be marketing slides, as long as each set keeps its in-use majority.

### Screenshot sizes

App Store Connect validates pixel dimensions exactly. Files are PNG or JPEG, RGB, no alpha channel, 1–10 per device size.

| Display | Portrait | Status |
|---|---|---|
| iPhone, medium display (6.3") | 1206 × 2622 or 1179 × 2556 | Required for every iPhone app |
| iPhone, large display (6.9") | 1320 × 2868 | Optional; App Store Connect can scale it down into the required slot |
| iPhone Duo, outer display | 1398 × 2034 | Own slot; see below |
| iPhone Duo, inner display | 2007 × 2853 | Own slot; see below |
| iPad 13" | 2064 × 2752 | Required for iPad apps |

Landscape uses the same numbers swapped.

**iPhone Duo needs its own set.** It has one slot per localization, which takes either the outer or the inner size, and App Store Connect does not scale other screenshots into it. Neither Duo size shares an aspect ratio with a regular iPhone: the inner display is about 7:10, closer to an iPad than a phone. So a scaled or letterboxed iPhone set is not a Duo set — lay the captions and UI out again for the wider canvas, and capture real Duo UI from a build that supports the device.

Multiple third-party guides report that Duo screenshots become required for submissions from April 2027 (some tie it to building with the iOS 27.1 SDK or later). That date is not confirmed from Apple's own pages here — check App Store Connect before planning around it. The Duo set is judged by the in-use gate like any other set.

## App icon

The icon appears in every search result and is the highest-ROI single asset test: icon optimization averages a 22.8% conversion uplift in SplitMetrics benchmarks — more than any copy change.

- Since April 28, 2026 all submissions must build with the iOS 26 SDK, so Liquid Glass icons are mandatory territory: the icon must be a layered artwork, not a flat PNG. A flat 2024-era icon still renders but looks dated next to native layered icons — a silent conversion tax in every search result.
- Design and check the icon in all six appearance modes: Default, Dark, Clear Light, Clear Dark, Tinted Light, Tinted Dark. An icon that only works in one mode is broken in five.
- Icon changes require a new app binary — plan icon A/B tests around release cycles (see Product page experiments).

## Preview video

Apple auto-plays preview videos muted in search results — an app without one shows a static frame where competitors show motion. Up to 3 previews, 30 seconds max each. Rules:

- Lead with the strongest moment. Never open with a logo, intro, or fade-in — there are 3 seconds before the user scrolls.
- Always add text overlays; the video plays muted.
- Show the app doing something, never a marketing sizzle reel. Apple requires previews to show actual app footage.
- 15–30 seconds total.

## Creative assets

Introduced at WWDC26, live on the store with iOS 27 and iPadOS 27. Screenshots and previews show the app *in use*; creative assets carry brand, seasonal offerings, and new content. Different job — never repurpose one as the other.

| Placement | What it is | If you skip it |
|---|---|---|
| Product page header | Image or video at the top of the listing, the first thing a visitor sees | The page opens on screenshots |
| Search results creative | The app's first impression in the Search tab, before anyone reaches the product page | Apple falls back to In-App Events, then previews, then screenshots |

The header is not an In-App Event card (those stay mid-page), not Today editorial, and not a paid ad slot. The search results creative is optional.

- **Build one universal creative first.** A single asset can serve the header, search results, and Apple Ads — and the same asset attaches to CPPs and to PPO header tests.
- **Upload through the Asset Library in App Store Connect.** Submit alongside a new app version, or separately in the Asset Library — independently of an app submission. The icon, by contrast, still changes only with a new binary.
- **Static image first.** Use video only if it reads muted and loops cleanly.
- **One clear idea, aimed at a first-time visitor.** The header is not the place to summarize the feature list.
- **Skip the header when screenshot 1 is already the hero** and there is nothing new to say. An empty slot beats a redundant one.

Since the October 16, 2026 revision of the App Review Guidelines, creative assets have their own guideline, **2.3.14**: they must relate to the app's content and functionality or its overarching brand, follow standard metadata rules, and suit all audiences — no inappropriate content, no references to other apps meant to mislead, no unverifiable claims, no specific or discounted prices.

Keep creative assets out of the screenshot count. Apple has not said whether the in-use gate applies to them, so a header never makes up for marketing-heavy screenshots: each screenshot set must pass the gate on its own.

Every creative asset must pass a **4+ age rating even when the app is 17+**. Apple rejects: pricing or discounts, URLs, copyright marks, unverifiable awards, logos or references to rival storefronts, and any Apple badge (Editor's Choice, App of the Day, Game of the Day, Apple Design Award).

Creative assets are a conversion lever, not a ranking lever. Apple has not said header or search creative content is indexed, so never treat either as keyword surface — the screenshot rules above are unchanged.

## Ratings

The star rating shows in search results before anyone visits the page. A 4.5★ app converts 30–40% better than a 3.8★ app on the same keyword and creatives — below 4.0, better metadata cannot win the conversion battle. Fix the rating first, then aim for 4.5+.

- Trigger the native prompt (`SKStoreReviewController` / `RequestReviewAction`) only after a success moment: task completed, milestone hit. Never after a crash, never on first launch — the prompt captures the user's current emotional state, and Apple has been rejecting first-launch prompts since 2026.
- The system shows the prompt at most 3 times per 365 days per device — the API can be called anytime but the OS decides. Those 3 impressions are the entire budget; spend them only on high-emotion moments.
- Never gate features or content on leaving a rating (Guideline 3.2.2).
- Respond to negative reviews within 48 hours. Users can update their rating after seeing a response; a thoughtful reply flips 2-star reviews into 4-star ones.
- If 30+ reviews mention the same bug, fixing it is ASO work. Mention the fix in the update notes — reviewers notice.
- Asking for reviews in release notes is allowed and effective ("If you find X helpful, leaving a review really helps us out").

## Tags

Apple generates public-facing tags for every listing from metadata, AI analysis, and editorial curation. You cannot create tags — but you can manage them, and unmanaged tags misdescribe apps.

- Review generated tags in App Store Connect and deselect any that misrepresent the app — a wrong tag routes wrong-intent traffic that bounces, and human reviewers approve tags before they go live, so corrections stick.
- Tag changes need no new build.
- Attribution: installs from a searched tag count as Search traffic; installs from browsing tag results count as Browse — check both when measuring.
- Recheck tags quarterly and after every description or screenshot change, because those are the inputs Apple generates from.

## Localization

Each additional locale gets its own title, subtitle, and keyword field — extra indexed characters at zero code cost, because storefronts cross-index specific locale pairs. The US storefront indexes en-US *plus* es-MX metadata; the UK indexes en-GB plus en-AU. Filling the cross-indexed locale with additional English keywords effectively doubles the indexed surface for that storefront. This is the most underused lever in indie ASO — but it's undocumented gray-area behavior Apple could close, so never put must-rank keywords only there.

- Configure 3–5 additional locales (e.g. Spanish (Mexico), French (Canada), Portuguese (Brazil)) even for an English-only app.
- Never just translate the English keywords — research what each market actually searches; direct translations miss local phrasing.
- Zero-overlap applies across cross-indexed locales too: a word already indexed from en-US is wasted in es-MX.
- Localized metadata also qualifies the app for regional featuring (see Featuring nominations) — editorial competition in smaller markets is far below the US.

## In-app events

Events are a reinforcement surface, not new keyword territory: an event will not rank the app for terms absent from its name and subtitle — the event name and short description strengthen the existing keyword footprint.

- Event cards surface in search results and on the product page even for users who already installed the app, making events the only listing surface that re-engages existing users.
- Run events for real occasions (launches, seasonal content, challenges) — they also feed semantic ranking as a structured activity signal, and an approved event is the strongest attachment for a featuring nomination.

## Promoted in-app purchases

Up to 20 IAPs or subscriptions can be promoted, each with its own display name (30 chars) and description (45 chars). Promoted non-consumables appear in App Store search results as their own entries — a free extra search presence most subscription apps never configure. Whether IAP names are keyword-indexed is unconfirmed, so write them as plain-language offers ("Annual Pro — unlimited exports"), never keyword slots. All IAP promotional metadata is editable anytime without a release, making it one of the few discovery surfaces you can iterate between versions.

## Product page experiments

Two App Store Connect features multiply the single default listing — use both before concluding "the metadata doesn't work":

- **Product page optimization (A/B tests):** up to 3 treatments against the default page, testing icon, screenshots, previews, or product page header visuals (not text). Only icon tests require a new app binary; screenshot, preview, and header tests ship without a release. Tests run up to 90 days at a 90% confidence threshold — always test one variable at a time or the winner teaches nothing.
- **Test creatives before copy.** Creative tests (icon, screenshots, previews, header) deliver 10–25% conversion lifts; copy iterations deliver 2–8%. Spend testing slots on assets first.
- **Custom product pages:** up to 70 per app, each with its own screenshots, promo text, and previews, each with its own URL and (since iOS 18) deep link. CPPs can be assigned their own keywords and rank in organic search — one keyword *theme* per page, so each page answers one intent — and a CPP must be localized for a market to appear in that market's search results. Apple's own data shows a 2.5-percentage-point conversion lift when traffic lands on a matching CPP instead of the default page.

## Featuring nominations

Editorial featuring (Today tab, category features) is free reach most indies never apply for. Nominations are submitted in App Store Connect.

- Submit at least 3 weeks before the moment; up to 3 months ahead widens consideration.
- Three nomination types: App Launch, App Enhancements (major updates), New Content (seasonal campaigns, events, offers). Pick the one that matches — a bug-fix release or UI refresh with no functional change never gets featured.
- Editors screen for UX quality, accessibility, localization, adoption of new Apple APIs, and a rating ≥ 4.0 — fix those before nominating, not after a rejection.
- Give editors a timing hook they can schedule around: adoption of a new iOS API, a holiday tie-in, an in-app event with a date. "The app is good" is not a hook.
- Attach an approved in-app event, and use all 5 supporting-URL slots (TestFlight links count).
- Nominate in smaller localized markets too — regional featuring bars are far lower than the US, and localized metadata is the qualifier.
- Featuring is a spike, not a channel — a Game of the Day slot has driven +470% organic installs for about a week, then decay. Time nominations to moments the listing can convert, and never plan revenue around recurring featuring.

## Paid + organic flywheel

Apple's algorithm needs download velocity to rank an app, but the app needs rank to get downloads. Pure organic ASO rarely breaks this cold start. Paid installs don't buy organic rank directly — no credible source claims that — but they raise keyword-level download velocity and conversion, which the organic algorithm weighs.

Before spending: minimum viable ASO first — primary keywords placed in name/subtitle, screenshot tap-through above ~25%, rating above 4.0. Paid traffic landing on a broken listing buys data, not downloads.

Pre-orders bank launch velocity for free: a pre-order page (available 2–180 days before release) ranks in search during the window, and every pre-order auto-downloads on release day — a concentrated day-one download spike the algorithm reads. Launching without pre-orders throws that spike away.

1. Run Apple Ads (renamed from Apple Search Ads in April 2025; placements expanded again in March 2026) at $10–20/day on the same keywords being optimized organically.
2. Structure in two campaign types: a **brand campaign** on your own name (competitors bid on it; defend it cheaply) and a **discovery campaign** (broad match + Search Match). The discovery campaign's goal is intelligence, not volume — you are paying Apple to reveal exactly what users type when they want an app like yours.
3. Feed converting search terms from discovery back into organic metadata.
4. Scale paid down as organic climbs.

Paid is the push that starts the flywheel; organic keeps it spinning.

## Metadata change mechanics

Name, subtitle, keyword field, description, screenshots, previews, and categories are version-locked — they change only with an app release. Promotional text, pricing, IAP metadata, tags, CPPs, and creative assets (via the Asset Library) are editable anytime. Consequences:

- Batch indexed-metadata changes into every release; between releases, iterate only on the anytime-editable surfaces.
- Plan seasonal keywords one release ahead: seasonal queries spike hard (holiday terms run ~9× normal volume for a week) and a version stuck in review misses the window. Cover the moment itself with in-app events, promo text, and CPPs.
- After a metadata release, expect 24–72 hours of partial re-indexing and 1–2 weeks of ranking volatility before things settle (industry estimate, not Apple-confirmed) — which is why a change is judged at the 2–4 week mark, never day one.

## Iteration loop

ASO is a monthly habit, not a launch task. Ranking changes from a metadata update show in 2–4 weeks; full results take 2–3 months — judge a change at the first mark, not the day after. Every 2–4 weeks:

- Check keyword movement; a keyword with no movement after 2 cycles gets replaced from the reserve list.
- Track: keyword rankings, search impressions, tap-through rate, conversion rate, organic vs. paid split.
- Read the numbers correctly: App Store Connect conversion rate = downloads ÷ unique *impressions* (not product-page views), and the "App Store search" source *includes Apple Ads taps* — derive true organic search by subtracting ads installs, or the flywheel looks healthier than it is.
- Compare against App Store Connect peer group benchmarks (25th/50th/75th percentile conversion, retention, crash rate) to tell whether the weak link is discovery or the page itself.
- Read recent reviews for new keyword ideas — users describe the app in the words other users will search.
- Quarterly: re-review generated tags (see Tags) and check the icon against current-OS icon styles.

## Audit checklist

When reviewing an existing listing, check in this order:

- [ ] Diagnosed which axis is weak — ranking (low impressions) or conversion (low downloads per impression) — and stated it before proposing changes
- [ ] Name uses all 30 chars and contains the primary keyword
- [ ] Zero word overlap across name / subtitle / keyword field
- [ ] Keyword field: ≥95 of 100 chars, no spaces after commas, singular only, no name/developer/category words, no trademarks or competitor names
- [ ] No filler words ("app", "free", "best", "the") in any indexed field
- [ ] Metadata reads as natural language answering one intent per field — not a token list
- [ ] Screenshot 1 states the main benefit; every screenshot has a caption in searchable feature language, none keyword-stuffed
- [ ] App Review gate: every set (each device type × each localization) has more than half of its screenshots showing the app in use — reported per set with the count, not "looks fine"
- [ ] Screenshot sizes match the current required slots (6.3" iPhone; 13" iPad for iPad apps), and an iPhone Duo set is designed for its own aspect ratio, not scaled from iPhone
- [ ] Icon is a layered Liquid Glass artwork checked in all six appearance modes
- [ ] Preview video exists, opens on action, has text overlays, 15–30s
- [ ] Product page header and search results creative are in place and pass the 4+ content rules, or deliberately skipped with a stated reason
- [ ] Rating ≥ 4.0 (target 4.5+) with a success-moment prompt in place (3 system prompts/year is the whole budget)
- [ ] Generated tags reviewed; misrepresentative ones deselected
- [ ] At least 3 additional locales configured with researched (not translated) keywords, including the storefront's cross-indexed locale
- [ ] Description names the category and core use cases in plain words (feeds Apple's tag generation)
- [ ] Subscription/IAP apps: promoted IAPs configured with plain-language offer names
- [ ] A creative A/B test is running or queued; recurring content uses in-app events; next featuring nomination has a date and a hook
