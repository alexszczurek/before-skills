---
name: aso
description: Write, audit, or improve an iOS App Store listing — app name, subtitle, keyword field, screenshots, preview video, ratings strategy, and localization. Use when creating or reviewing App Store metadata, doing keyword research, planning a metadata update, or when the user mentions ASO, App Store Optimization, app store listing, keywords, subtitle, screenshot captions, preview video, ratings prompt, or Apple Search Ads.
---

# App Store Optimization

You are optimizing an iOS App Store listing. 70% of App Store visitors find apps through search and 65% of downloads happen immediately after a search — the listing does more selling than the landing page. Every rule below exists because the search algorithm indexes exactly three text fields, and everything else is a conversion tool, not a discovery tool.

## The only fields that rank

Apple indexes exactly 160 characters for search. Never spend effort "optimizing the description for keywords" — the description and promotional text (170 chars, updatable without a new version) are NOT indexed. They affect conversion, not discovery. One nuance since iOS 26: Apple's LLM generates App Store *tags* from the description and screenshots, so the description should still name the app's category and core use cases in plain words — for the tag generator, not for keyword rankings.

| Field | Limit | Keyword weight | Visible to users |
|---|---|---|---|
| App Name | 30 chars | Highest | Yes |
| Subtitle | 30 chars | Second | Yes |
| Keyword Field | 100 chars | Third | No |

Also indexed: category, in-app event names, and (per strong 2025 industry evidence, not Apple-confirmed) screenshot caption text.

**The zero-overlap rule:** never repeat a word across any of the three fields. Apple combines tokens across all fields, so a duplicated word is a wasted slot that could have covered a new search query. When auditing a listing, check this first — it is the most common and cheapest-to-fix error.

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
- It must read as a sentence fragment a human would write. A keyword-stuffed subtitle tanks tap-through rate because users see it before they tap — a ranking gain that kills conversion is a net loss.

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
5. **Distribute**: top keyword → name, complementary terms → subtitle, everything else → keyword field, zero overlap between fields.

Pick 15–20 keywords for the first update and hold 15–20 in reserve — underperformers get swapped after 4–8 weeks, and having a bench ready is what makes iteration actually happen.

## Screenshots

Screenshots are advertisements, not documentation. Raw UI captures are a photo album, not optimization — users scan captions at thumbnail size and never study the UI. Only 1–3 screenshots show in search results, and only two device sizes are required (6.9" iPhone, 13" iPad — everything else scales down).

Every screenshot gets a bold text caption at the top — captions drive scanning, and there is strong 2025 evidence Apple indexes caption text, making captions keyword surface too. Assign jobs by position (max 10 slots):

| Position | Job |
|---|---|
| 1 | Main benefit — the only one most users ever see |
| 2 | Differentiation from alternatives |
| 3 | Trust signal — award, press, user count ("Apple Watch App of the Year") |
| 4–6 | Core features solving real problems |
| 7–8 | Recent features — proof the app is alive |

## Preview video

Apple auto-plays preview videos muted in search results — an app without one shows a static frame where competitors show motion. Up to 3 previews, 30 seconds max each. Rules:

- Lead with the strongest moment. Never open with a logo, intro, or fade-in — there are 3 seconds before the user scrolls.
- Always add text overlays; the video plays muted.
- Show the app doing something, never a marketing sizzle reel. Apple requires previews to show actual app footage.
- 15–30 seconds total.

## Ratings

The star rating shows in search results before anyone visits the page. Below 4.0, better metadata cannot win the conversion battle — fix the rating first.

- Trigger the native prompt (`SKStoreReviewController` / `RequestReviewAction`) only after a success moment: task completed, milestone hit. Never after a crash, never on first launch — the prompt captures the user's current emotional state, and Apple has been rejecting first-launch prompts since 2026.
- The system shows the prompt at most 3 times per 365 days per device — the API can be called anytime but the OS decides. Those 3 impressions are the entire budget; spend them only on high-emotion moments.
- Never gate features or content on leaving a rating (Guideline 3.2.2).
- Respond to negative reviews within 48 hours. Users can update their rating after seeing a response; a thoughtful reply flips 2-star reviews into 4-star ones.
- If 30+ reviews mention the same bug, fixing it is ASO work. Mention the fix in the update notes — reviewers notice.
- Asking for reviews in release notes is allowed and effective ("If you find X helpful, leaving a review really helps us out").

## Localization

Each additional locale gets its own title, subtitle, and keyword field — extra indexed characters at zero code cost, because storefronts cross-index specific locale pairs. The US storefront indexes en-US *plus* es-MX metadata; the UK indexes en-GB plus en-AU. Filling the cross-indexed locale with additional English keywords effectively doubles the indexed surface for that storefront. This is the most underused lever in indie ASO — but it's undocumented gray-area behavior Apple could close, so never put must-rank keywords only there.

- Configure 3–5 additional locales (e.g. Spanish (Mexico), French (Canada), Portuguese (Brazil)) even for an English-only app.
- Never just translate the English keywords — research what each market actually searches; direct translations miss local phrasing.
- Zero-overlap applies across cross-indexed locales too: a word already indexed from en-US is wasted in es-MX.

## Product page experiments

Two App Store Connect features multiply the single default listing — use both before concluding "the metadata doesn't work":

- **Product page optimization (A/B tests):** up to 3 treatments against the default page, testing icon, screenshots, or previews (not text). Only icon tests require a new app binary; screenshot/preview tests ship without a release. Tests run up to 90 days at a 90% confidence threshold — always test one variable at a time or the winner teaches nothing.
- **Custom product pages:** up to 70 per app, each with its own screenshots, promo text, and previews, each with its own URL and (since iOS 18) deep link. CPPs can be assigned their own keywords and rank in organic search, and serve as ad variations in Apple Ads — build one per major use case or audience instead of one page that averages across all of them.

## Paid + organic flywheel

Apple's algorithm needs download velocity to rank an app, but the app needs rank to get downloads. Pure organic ASO rarely breaks this cold start. Paid installs don't buy organic rank directly — no credible source claims that — but they raise keyword-level download velocity and conversion, which the organic algorithm weighs. The sequence:

1. Run Apple Ads (renamed from Apple Search Ads in April 2025) at $10–20/day on the same keywords being optimized organically.
2. Use ads data to find which keywords *convert*, not just rank.
3. Feed converting keywords back into organic metadata.
4. Scale paid down as organic climbs.

Paid is the push that starts the flywheel; organic keeps it spinning.

## Iteration loop

ASO is a monthly habit, not a launch task. Every 2–4 weeks:

- Check keyword movement; a keyword with no movement after 2 cycles gets replaced from the reserve list.
- Track: keyword rankings, search impressions, tap-through rate, conversion rate, organic vs. paid split.
- Read recent reviews for new keyword ideas — users describe the app in the words other users will search.

## Audit checklist

When reviewing an existing listing, check in this order:

- [ ] Name uses all 30 chars and contains the primary keyword
- [ ] Zero word overlap across name / subtitle / keyword field
- [ ] Keyword field: ≥95 of 100 chars, no spaces after commas, singular only, no name/developer/category words, no trademarks or competitor names
- [ ] No filler words ("app", "free", "best", "the") in any indexed field
- [ ] Screenshot 1 states the main benefit with a caption; every screenshot has a keyword-bearing caption
- [ ] Preview video exists, opens on action, has text overlays, 15–30s
- [ ] Rating ≥ 4.0 with a success-moment prompt in place (3 system prompts/year is the whole budget)
- [ ] At least 3 additional locales configured with researched (not translated) keywords, including the storefront's cross-indexed locale
- [ ] Description names the category and core use cases in plain words (feeds Apple's tag generation)
- [ ] A screenshot/preview A/B test is running or queued; recurring content uses in-app events (event names are searchable)
