# Source: https://pokpok.ai/admin/changelog

###### ON-DEMAND BRAND PERCEPTION ALIGNMENT ANALYSIS

# Product _Updates_

What's new, what's fixed, what's coming

Pending Diagnostics

45/77 open

\[ \]5 Truth prompt refactor — mirror AI GEO (Gemini 3 Flash) pattern: add <PRE\_COMPUTED> echo contract (deterministic min/max/divergence/cohorts in n8n Code node), trim ~30%, save as v2\_gemini-3-flash + example\_output.json + pre\_compute\_node.js. Save-only; user deploys n8n. \[TODO migrated from session-start fallback — admin\_todos MCP unreachable\]

\[ \]Admin /todo page + TodoLoader code component — full CRUD on new Supabase \`admin\_todos\` table (admin-allowlist RLS). Replace markdown TODO block inside /admin/changelog (ChangelogLoader v2.6.0, Supabase-backed) so both pages share a single source of truth. New table at \`xray/supabase/migrations/006\_admin\_todos.sql\`. \[2026-04-21\]

\[✓\]UniversalDataProvider (Framer) — code component with property-controls UI panel, GitHub+Supabase data source picker. Live on /products/single-pdp-reports/brand-perception/brand-perception-truth via codeFileId \`cqhovi4\` (v1.7.0). 17 Evidence Item instances + The Battlefield Frontline (\`bAmZ5rfrF\`) all bind via DataOverrides.Data. Full interactive WWW analysis flow shipped 2026-04-22. \[2026-04-21 → 2026-04-22\]

\[ \]Brand Perception WWW V4 sandbox iteration — created copy \`52lZstOsQMhgspl8\` (WIP). Cross-brand evaluation across 4 URLs (tatcha/warbyparker/notion/allbirds) revealed 3/4 brands silently halted at \`Clean relevant urls\` due to hardcoded \`tatcha.com\` in \`Relevant URLS\` HTTP node body. Patches v3-v6 deployed: (v3) prompt LEGACY MAPPING + temp=0 on 3 Gemini nodes; (v4) parser stage redesign — single Firecrawl + Code post-processor (drops 3-way scrape + 2 Gemini merger calls); (v5) screenshot stack collapsed 6→2 active nodes (HTTP primary + ScrapingBee fallback); slim AI GEO context (~80KB→~5KB user prompt); (v6) added Merge + Combine HI+GEO Code node fusing 17-marker + AI/GEO outputs into single clean JSON \`{brand, url, hi:{}, ai\_geo:{}}\`. Total nodes 82→64. Tatcha A/B PRE-PATCH 3/5 → POST-PATCH 4/5 on 17-marker quality. Per-brand reports + master report in \`n8n/web analysis/new-workflows/runs/2026-04-26\_v4-node-comparison/\`.

\[✓\]Brand Perception WWW V3.3 — sitemap-driven brand analysis (workflow \`VU4VKleSgaZZJWyH\`, active). Split-architecture: Clean Sitemap regex-detects products vs narrative candidates (caps at 5 products, 200 narrative entries); Classify URLs (Gemini 2.5-flash, thinkingBudget=0, maxOutputTokens=8192) picks about/mission/vision/values/positioning/manifesto from narrative list; Fan Out 8 URLs normalizes + dedupes URLs (skips homepage — visual path covers it); Scrape Relevant Page pulls full markdown per URL; Aggregate emits full \`brand\_content\` map (no truncation, no snippets — full markdown dominates prompt). Screenshot: 3-tier fallback (Firecrawl basic → Firecrawl Premium/stealth proxy → ScrapingBee) feeds \`Analyze an image\` via binary-mode Gemini. Prompts wraps content in \`<BRAND\_CONTENT\_FULL\_MAP>\` + \`<VISUAL\_DATA\_SOURCE>\`. Tested on pokpok.ai, patagonia.com, liquiddeath.com — all 8 stages verified. Per-brand cost: small $0.15, large $0.34. Failures logged: F078 (n8n sandbox no URL ctor), F079 (Gemini imageUrls rejects data: URLs), F080 (3-tier screenshot fallback).

\[ \]Handwritten font — improve glyph vector tracing accuracy (5-phase plan: measurement infra → filled adaptive threshold → corner-aware smoothing → stroke v3 continuous paths → varstroke oriented ellipse)

\[ \]Handwritten font — write status/todo/plan (Phase A: manual relabel; Phase B: PACK→K shape fix; Phase C: font assembly v1) \[2026-04-12\]

\[✓\]Handwritten font extraction v11 — reading-order labels + word-gap alignment + y\_tol stray filter + rasterize+potrace varstroke + interactive relabel UI. User validated "accuracy is much higher now" (2026-04-12)

\[ \]Handwritten font — Phase A manual relabel pass (219 glyphs, ~70-80% label accuracy ceiling, need ≥95% for font v1)

\[ \]Handwritten font — Phase B fix PACK→K corrupt shape (horizontal bar vs two diagonals) + re-verify OF→O

\[ \]Handwritten font — Phase C font assembly v1 (baseline alignment, advance widths, aalt/salt/liga features)

\[✓\]Handwritten font pipeline — cc.png-based extraction working end-to-end (219 glyphs/33 chars), filled+stroke SVGs, interactive tester with hide-photo toggle (2026-04-12)

\[ \]Handwritten font — perspective correction automation (manual for now, 32 attempts failed)

\[ \]Pixel sprite transition Framer component — dgrees.studio style grid with staggered wipe animation. v1.5.2: fill/crop sampling, IO+RAF scroll, speed prop, auto-sizing

\[✓\]Awtrix 3 integration — POKPOK Index top 2 movers with full metrics on Ulanzi pixel clock + web emulator component

\[ \]Awtrix daily launchd timer — auto-push latest.json to device on schedule

\[ \]Deploy AwtrixEmulator to Framer pokpok-index page

\[ \]Homepage HTML redesign — evaluate and rebuild pokpok-ai.html to match pokpok-ui design system

\[✓\]X-RAY share not including screenshot and direct link to report session — 3 bugs (B28+B29+B30) fixed in XrayOverrides v1.12.1, deployed + verified 2026-03-31

\[✓\]Brand LinkedIn Finder — found 25 decision-makers across 9/12 index brands via Tavily, saved to marketing/brand-contacts.md + Supabase brand\_contacts table. Remaining: e.l.f., COLOR WOW, Secret

\[✓\]Supabase brand\_contacts table — migration applied, 25 contacts inserted with dedup on linkedin\_url

\[✓\]brand-linkedin-finder agent + skill created — reusable for monthly index updates

\[✓\]Outreach restructure — moved linkedin-outreach-sequence.md, lead-list.md, brand-contacts.md/.json to marketing/outreach/. Updated 9 files with new paths.

\[✓\]brand-linkedin-finder v2 — rewrote agent+skill as "Lead Generation & Corporate Research Specialist". New per-brand JSON output: brand\_identity + contacts\_and\_leads + additional\_corporate\_info. Saves to marketing/outreach/brands/{slug}.json

\[✓\]Brand research run v1 (2026-04-09) — 59 contacts across all 12 index brands via WebSearch. 57/59 LinkedIn URLs verified correct via Chrome DevTools. Per-brand JSON in marketing/outreach/brands/

\[✓\]Brand research run v2 (2026-04-09) — 61 contacts across all 12 index brands via ScrapingBee Google SERP. All URLs from Google's index (verified by source). 24% fewer tokens, correctly filtered departed employees. Per-brand JSON in marketing/outreach/brands/v2/

\[✓\]brand-linkedin-finder switched to ScrapingBee-first — Google SERP for LinkedIn URLs (10 credits, real indexed URLs), scrape About pages (1 credit). WebSearch as fallback for names only. Agent+skill updated.

\[✓\]V2 contacts inserted into Supabase brand\_leads table — 61 rows from SB run. Total 86 rows (incl. 25 pre-existing). Service role key saved to ~/dev/.env

\[✓\]Fixed non-Shopify gallery scraper — added generic fallback with extract\_rules + stealthProxy for brands like Dove/Unilever (sub-workflow n8lYVrcIB4DqCngo)

\[ \]Error tracking system — deploy scan-url-v2 v7 edge function, paste RecurringOrderItemsList v1.3.9 + AdminPDPProvider v1.5.20 to Framer, configure n8n Error Workflow, schedule timeout cron

\[ \]X-RAY Phase 3.2: Native LinkedIn Share + Dynamic OG Cards — implement share-og edge fn, screenshot upload, native LinkedIn dialog, remove LinkedIn OAuth

\[ \]X-RAY OG image quality fix — fix og:image:width/height mismatch (1200x630 declared vs 3122x1502 actual), deploy claim-share-bonus v4 with GitHub Pages push, set GITHUB\_TOKEN

\[✓\]X-RAY credit system — full deployment (SQL migration, edge functions, Provider v1.5.0, Overrides v1.9.0)

\[✓\]X-RAY credits display fix — refreshCredits() 401 fixed (raw fetch → Supabase client), event name mismatch fixed (Provider v1.5.2, Overrides v1.9.6)

\[ \]X-RAY credits idempotency — migrateDoneRef guard to prevent duplicate +1 on repeated auth events (Provider v1.5.3 ready, awaiting deploy)

\[ \]X-RAY: \[SIGN IN +1\] CTA still visible for authenticated users — should hide after sign-in

\[ \]Consolidate audit docs — OPEN-ISSUES.md created, architecture-flaws-report.md updated, obsolete docs deleted, all statuses set to WIP

\[ \]Full code audit complete — 6 CRITICAL, 25 HIGH, 45+ MEDIUM. Report: www/docs/plans/CODE-AUDIT-2026-03-09.md

\[ \]\[CRITICAL\] C1: OrderFormProvider WEBHOOK\_URL undefined — "Send to Analysis" broken at runtime

\[ \]\[CRITICAL\] C3: PaywallModal references dead Kinde auth — login button hangs

\[ \]\[CRITICAL\] C4: RealtimeTickerOverride wrong Supabase key + hardcoded debug execution\_id

\[✓\]\[X-RAY\] B25: YOUR SCORE clickable — Framer container disabled via mergedRef (v1.11.9)

\[✓\]\[X-RAY\] B26: Dial no-toggle — removed re-click toggle, OFF is dedicated zone (v1.11.9)

\[✓\]\[X-RAY\] Share clipboard copy — moved before async ops to keep user gesture context (v1.11.9)

\[✓\]\[X-RAY\] Share domain "unknown" — reads scanUrl from nav global (v1.11.9)

\[✓\]\[X-RAY\] SHARE\_OG\_BASE → xray.pokpok.ai custom domain (v1.11.9)

\[✓\]\[X-RAY\] xray.pokpok.ai redirect to pokpok.ai/products/xray (GitHub Pages)

\[✓\]\[X-RAY\] Migrate share pipeline from xclv-ai/pokpok-report → pokpok-ai/xray + xray.pokpok.ai custom domain

\[ \]\[X-RAY\] B27: Roast shows "not available" for landor.com despite data existing in Supabase

\[ \]\[CRITICAL\] C5: Payment system in sandbox mode (USE\_PRODUCTION=false, sandbox Polar URLs)

\[ \]\[HIGH\] Open redirect chain — unvalidated \`return\` param in AuthOverrides, AuthOrderOverride, NavAuthButton

\[ \]\[HIGH\] Plaintext password stored on window.\_\_POKPOK\_SIGNIN\_STATE\_\_

\[ \]\[HIGH\] Unauthenticated n8n webhook URL exposed in 6 client-side files

\[ \]\[HIGH\] \`return null\` from 9 Framer Code Components — violates F002, breaks layout

\[ \]\[HIGH\] Supabase realtime channel leaks in DashboardDataProvider + AdminPDPViewerOverrides

\[✓\]Save all Framer live code files to local backup folder (2026-03-09-framer-live)

\[ \]\[WIP - awaiting user verification\] SubscriptionCheckoutButton v1.1.0 — fix signin redirect delay (1800ms) so "YEAH!" button variant is visible before navigation

\[✓\]Clean marketing table — delete codex QA records + deduplicate emails

\[ \]Deploy www\_system\_prompt\_v4.6 to n8n + test B0BPXT3GBN (Marker 8 fix)

\[ \]Fix scoring non-determinism — move alignment formula from Gemini to Code node

\[ \]Fix system prompt v3.5/v3.6 — broken UI data format (territory\_number string, archetype prefix)

\[ \]WWW v2 — test 1+ more brands (2/3 complete), validate downstream consumption

\[ \]Update \`pdp\_intro\_2.0.md\` evidence paths for v2 visual analysis schema

\[ \]Update \`www\_intro\_2.0.md\` evidence paths for www v2 schema (Marker 8 references)

\[ \]Test PDP v2 output across 3+ ASINs for composition enum validation

\[ \]Deploy BestSellerCard click-to-run-analysis (v1.0.13 ready)

\[✓\]POKPOK Index March 2026 podcast — NotebookLM audio overview (Feynman style, 17m49s)

\[✓\]Brand URL Discovery V5 (k5QSjquwAgeoNbfg) — full architecture redesign: AI-first URL classification, Firecrawl Agent for product gallery images, 4 pages scraped instead of 25

\[ \]Monthly aggregation workflow (top 15 products)

\[ \]Verify n8n webhook flow execution end-to-end

\[ \]Dynamic /order page (product context from source pages)

\[ \]Refactor: Move archetype SVGs from GitHub Pages to Supabase storage — all 12 uploaded to \`https://iyyuxilkacylpbweulsa.supabase.co/storage/v1/object/public/assets/archetypes/\`. Update \`ARCHETYPE\_SVG\_BASE\` in CategoryDataOverrides.tsx (codeFileId: OTlqFfg) and DataOverrides.tsx (codeFileId: PUwIdwd)

\[ \]Deploy security notification email templates to Supabase (email-changed, mfa-added, mfa-removed, password-changed)

\[ \]Fix n8n "Download Image" EPROTO error — Cloudflare Worker proxy deployed (\`amazon-image-proxy.pokpok.workers.dev\`), need to update n8n workflow URL

\[✓\]Admin page architecture fix — IndexImportProvider v1.1.1 (remove purchased\_reports from auto-import), DB cleanup done

\[✓\]RecurringOrderItemsList v1.3.8 — RUNNING badge hover shows ASIN number

\[✓\]AdminPDPProvider v1.5.19 — auto-flag PDPs with alignment < 40

2026-05-08

// Polar env unification + n8n V3.10 user\_id fix + DB backfill + OrderList notch color

\[✓\]curen8n V3.10 (\`Ca58L0pbclwDYwUw\`) \`Extract Data.user\_id\` was reading \`data.user\_id\` (Polar customer\_id) instead of \`data.metadata.reference\_id\` (Supabase auth.uid). Every paid order since the V3.x rewrite stored the wrong \`user\_id\`, causing OrderList (which queries \`WHERE user\_id = auth.user.id\`) to silently filter rows out. Fix: change one expression on the live Extract Data node, published. All future orders write the correct uid.

\[✓\]cureDB backfill — deleted older pokpok.ai duplicate row (May 6, satisfies \`(user\_id, slug)\` unique constraint) + updated 2 rows for \`ceo@xclv.com\` from Polar customer\_id \`bf774dc1-...\` to Supabase auth.uid \`c84ed39d-...\`. Verified in DevTools — both \`pokpok.ai\` (May 7) and \`dragonrouge.com\` (May 8) rows now visible in OrderList.

\[✓\]new scanEdge function \`polar-checkout-www\` v3 deployed (Supabase). Accepts \`x-pokpok-env: sandbox|prod\` header (mirrors \`polar-customer-portal\` v1.3.0 contract); picks per-env Polar checkout link from secrets \`POLAR\_WWW\_CHECKOUT\_LINK\_PROD\` / \`\_SANDBOX\`; legacy fallback for prod (existing secret) keeps backwards-compat. Default = prod when no hint. Verified via DevTools curl matrix: no-hint → prod, prod → prod, sandbox → 500 expected (sandbox secret not yet set).

\[✓\]new scan\`WebhookButton\_v4.2.0.tsx\` (local, awaiting paste) — sandbox toggle drives \`x-pokpok-env\` HTTP header instead of picking a function name. Drops 2 dead Property Controls (\`polarSandboxFunction\` / \`polarProductionFunction\`) that pointed at phantom edge functions \`polar-checkout-www-sandbox\` (never deployed). One function for both envs.

\[✓\]new scan\`OrderList\_v2.1.7.tsx\` deployed + verified working — adds \`notchColor\` Property Control (Color picker) in canvas. Recolors the 4 corner-square notches on every chip in every Order row (VIEW REPORT button, date pill, PAID link). Implementation walks the rendered DOM post-render: finds \`\[data-framer-name="Rectangle 46"\]\` divs (canvas-set name, stable across builds) and sets \`style.backgroundColor\`. No Smart Component prop dependency.

\[✓\]cure\`DashboardDataProvider\_v3.5.0.tsx\` (local, awaiting paste) — removes hardcoded \`POLAR\_ENV = "sandbox"\` constant + \`x-pokpok-env: "sandbox"\` header. Was forcing the universal \`polar-customer-portal\` edge fn into sandbox-only lookup → prod customer 422 → 500 (visible in console twice per page load). Removing the hint lets edge fn use its built-in prod-first fallback.

\[✓\]cure\`OrderList\_v2.1.6.tsx\` (local, superseded by v2.1.7) — drops redundant \`x-pokpok-env: "prod"\` header + \`env: "prod"\` body field from the polar-customer-portal fetch. Edge fn auto-routes — explicit hints were unnecessary.

\[✓\]upgradeVerified Polar PROD + SANDBOX webhook URL via Polar API: both → \`https://xclv.app.n8n.cloud/webhook/polar-paymentV2\` (workflow \`Ca58L0pbclwDYwUw\` V3.10). Two other active polar-payment workflows (\`w61btrWPdIEArbAd\` V3.2 on \`/webhook/polar-paymentV3\` + \`Xnl1Dc4UVWFlzuP2\` original) are orphaned — Polar never calls them. Recommended deactivation pending user OK.

\[✓\]upgradeEdge function \`polar-checkout\` v18 (ASIN flow) — local file written but deployment deferred. v17 has hardcoded sandbox URL, but no prod ASIN/Brand Alignment checkout link exists yet. Deploy with \`POLAR\_PDP\_CHECKOUT\_LINK\_PROD\` secret when ready.

\[✓\]upgradeFailure registry updated — \`pokpok-ai/.claude/skills/framer/references/failures.md\` adds F105 (picked stale local file as base because version-string sort lied — should have used \`ls -lt\` mtime sort, or \`readCodeFile\` from Framer MCP) and F106 (proposed schema-level n8n change without auditing all readers first — must grep all readers before proposing).

Today's verified end-to-end flow:

2026-04-22

// Brand Perception Truth — interactive WWW analysis flow

\[✓\]new scan\`WebhookButton.tsx\` v2.0.0 → v2.2.0 — new Framer code component replacing the legacy \`Proceed to Checkout\` submit button on \`/products/single-pdp-reports/brand-perception/brand-perception-truth\`. Reads URL from the form input, calls the \`validate-www-url\` edge function, POSTs \`{www\_link, slug, source}\` to the n8n \`brand-perception-www\` webhook, and dispatches \`pokpok-webhook-triggered\` so the provider can re-fetch. Brand-compliant per pokpok-ui spec: yellow \`#F5F900\` bg + teal \`#0A3B44\` text, JetBrains Mono 14px, 4× 4×4px corner notches in parent bg color, hover flip. Button height locked to 50 × 100% width (immune to Framer's injected \`height: 100%\`).

\[✓\]new scanSupabase edge function \`validate-www-url\` v2 — real reachability check, not just URL syntax. Auto-prepends \`https://\` for bare domains (\`pokpok.ai\`, \`xclv.com\`), rejects localhost/private ranges, performs HEAD/GET probe with 8s timeout, classifies \`<400\` valid / \`404\` invalid / \`5xx\` invalid / other 4xx valid (site up, just anon-blocked) / timeout+DNS fail invalid. Deployed to project \`iyyuxilkacylpbweulsa\`, verify\_jwt=false.

\[✓\]new scan\`WwwFormOverrides.tsx\` v1.0.0 → v1.1.0 — new Framer code file with two dedicated WWW-form overrides. \`WwwUrlInput\` debounces keystrokes 400ms, calls the edge function, broadcasts \`pokpok-www-validation\` events (states: idle / checking / valid / invalid). \`WwwValidationBadge\` toggles the Status component's visibility based on those events — hidden for empty / checking / valid, shown only when the edge function returned \`valid: false\`. Preserves the panel-set \`content\` prop (no text rewrite).

\[✓\]new scan\`UniversalDataProvider.tsx\` v1.5.0 → v1.7.0 (codeFileId \`cqhovi4\`) — two additive bumps. v1.6.0 adds opt-in Supabase realtime subscription on \`<realtimeTable>\` filtered by \`<realtimeUrlColumn>=eq.<watched>\`, listens for \`pokpok-webhook-triggered\` to re-open the channel with the submitted URL, re-dispatches \`pokpok-data-ready\` on INSERT/UPDATE. v1.7.0 adds \`Mirror WWW -> PDP\` panel prop (default true) that writes the fetched www payload to the \`pdp\` slot — this fixed \*\*The Battlefield Frontline\*\* (nodeId \`bAmZ5rfrF\`) and any other \`pdp\_\*\`-bound component on WWW-only pages. All 17 Evidence Items + Battlefield section now render real Bramley brand-perception data, not placeholder labels.

\[✓\]cureWebhookButton v2.1.0 rejected legitimate short domains (\`pokpok.ai\` = 9 chars) because of a strict \`length < 10\` client preflight. v2.2.0 drops the length floor (keeps 500-char ceiling as sanity rail), auto-prepends \`https://\` for bare domains, delegates the real validation to the edge function.

\[✓\]cureLegacy "PASTE A VALID AMAZON PRODUCT LINK TO CONTINUE" copy on the WWW page — the \`ValidationBadge\` override from \`Paywall/OrderFormProvider.tsx\` was hardcoding Amazon-specific text even on this WWW-only page. Replaced with \`WwwFormOverrides.WwwValidationBadge\`; the original PDP override and file are untouched so the brand-alignment page keeps working.

\[✓\]upgrade5 edge-function test scenarios verified via curl and 4 end-to-end browser scenarios verified via Chrome DevTools (empty / junk / valid / unreachable). Battlefield Frontline live-DOM confirmed rendering \`"Gentle Countryside Ritual"\` + \`"Nature's Gentle Wisdom"\` + full category summaries from the Bramley JSON.

Realtime subscription plumbing is in place but not yet activated on the canvas — to enable auto-refresh after a submitted URL is processed, set \`realtimeTable = www\_perception\` and \`realtimeUrlColumn = url\` on the UniversalDataProvider instance's panel. \`OrderFormProvider.tsx\` (PDP, frozen at \`b0btPSD\`) was not touched; brand-alignment page unchanged.

2026-04-12

// Handwritten Font Pipeline

\[✓\]new scanEnd-to-end extraction on \`cc.png\` (user-normalized) produces 219 glyphs across 33 chars with both filled and stroke SVGs per glyph

\[✓\]new scanInteractive tester (\`output/font-tester.html\`) — type preview, glyph gallery, overlay accuracy check with hide-photo toggle revealing pure red vector strokes on white

\[✓\]new scan\*\*ViktorHand.ttf\*\* — actual TTF font file (34 KB, 175 glyphs, 30 chars with up to 8 alternates each). OpenType \`aalt\` + \`salt\` features. Works in browser via \`@font-face\`. Preview: \`output/ViktorHand-preview.html\`

\[✓\]curePotrace bounding-box filter rejected 73% of legitimate glyphs — now requires contour to touch ALL FOUR edges, mask padded 2px (FF011)

\[✓\]cureOverlay stacking produced muddy strokes — separated into \`strokes\_only\_cc.png\` (transparent red strokes) + \`cc.png\` base layer with toggleable photo opacity (FF012)

\[✓\]cureStaircase/pixelated vector curves — was upscaling binary mask (cubic-interp on 0/255 only produces ringing); now dilates mask 3 px to capture gray halo, upscales \*\*grayscale\*\* 8x, thresholds upscaled gray. Potrace sees sub-pixel-smooth edges from the photo's natural anti-aliasing (FF013)

\[✓\]cureComparison render showed solid black boxes — PIL \`.convert("RGB")\` on RGBA fills transparent with black; now composite onto white using alpha channel as mask (FF014)

\[✓\]upgrade\`scripts/extract\_cc.py\` + \`scripts/rebuild\_cc\_tester.py\` + \`scripts/build\_font\_cc.py\` — single-command pipeline from photo to working font

Font v0.1 is functional. Polish pending: baseline normalization, per-glyph spacing tuning, OCR accuracy (tesseract → PaddleOCR), \`calt\` contextual alternates.

2026-03-31

// X-RAY Share Pipeline

\[✓\]cureScreenshot pre-capture timing — was capturing scanning animation ("finalizing results...") instead of final scores. Increased delay from 1.5s to 3s (B28)

\[✓\]cureClipboard share text now includes direct link to scan results (\`xray.pokpok.ai/shares/{id}.html\`) instead of generic \`pokpok.ai/products/xray/\` (B29)

\[✓\]cureRace condition — LinkedIn dialog opened before OG files pushed to GitHub Pages. Now awaits \`claim-share-bonus\` edge function before opening share dialog (B30)

XrayOverrides v1.12.1 deployed to Framer

2026-03-30

// Brand URL Discovery V5 — Architecture Redesign

\[✓\]new scanComplete V5 rewrite of Brand URL Discovery workflow (k5QSjquwAgeoNbfg) — moved from regex URL filtering to AI-first classification

\[✓\]new scanGemini 2.5 Flash classifies URLs from URL paths BEFORE scraping — no need to scrape 25 pages just to classify them

\[✓\]new scanFirecrawl Agent extracts product gallery images from product page — 6 real CDN images with alt text (replaces broken Firecrawl Extract + markdown regex)

\[✓\]upgradeOnly 1-6 selected pages scraped (down from 25) — faster, cheaper, more accurate

\[✓\]upgradeRemoved 4 nodes (Filter Candidate URLs regex, Extract Snippets, Firecrawl Extract Visuals, post-scrape Classify), added 3 (Classify URLs, Prepare Scrape List, Extract Product Images Agent)

\[✓\]cureGemini no longer duplicates URLs across mission/values/positioning — classification from URL paths is more decisive than from scraped content

2026-03-22

// n8n Gallery Scraper — Generic Fallback for Non-Shopify Sites

\[✓\]cureGallery image sub-workflow (n8lYVrcIB4DqCngo) failed silently on non-Shopify brands (e.g. Dove/Unilever) — all 3 Shopify scraping strategies returned 0 items, causing WWW evaluation to skip and alignment score to be garbage 0/100

\[✓\]new scanAdded generic fallback path: ScrapingBee \`extract\_rules\` (CSS selectors) + \`stealthProxy\` → new parser node → deduplication + alt-text extraction → feeds into existing Visual Analysis chain

\[✓\]cureDownload Image node dynamic Referer fix — CDN access controls (assets.unileversolutions.com) rejected requests without matching Referer header

\[✓\]upgrade6 new failure patterns documented (F045-F051): \`\_\_sbResult\` incompatibility, \`extract\_rules\` vs \`ai\_extract\_rules\`, stealthProxy requirements, CDN Referer headers, n8n expression gotchas

\[✓\]upgradeBackups saved: \`n8n/n8n-backups/www-gallery-v4-generic-fallback.json\`, \`parsing-generic-gallery.js\`, \`brand-perception-v3.2-www-guard.json\`

2026-03-21

// Error Tracking System — Full Audit + Implementation

\[✓\]new scanSQL migration 005\_error\_tracking — added error\_message, last\_execution\_id, last\_run\_at, flag\_reason to \`pdp\`; asin, error\_message, timeout\_at, retry\_count to \`executions\`; status, error\_message, n8n\_execution\_id, scan\_duration\_ms, roast\_status to \`free\_scans\`; CHECK constraint on \`purchased\_reports.status\`

\[✓\]new scan\`admin\_error\_dashboard\` VIEW — aggregates errors from pdp, executions, purchased\_reports, free\_scans into single queryable view

\[✓\]new scan\`timeout\_stuck\_executions()\` FUNCTION — auto-marks executions stuck >30min as 'timeout', propagates to pdp.status='error'

\[✓\]new scanRecurringOrderItemsList v1.3.9 — ERROR badge (red bg, "ERROR" text), hover→"RETRY", click→clear error + rerun webhook. RUN ALL also includes error ASINs.

\[✓\]new scanAdminPDPProvider v1.5.20 — errorCount in RecurringGroup, console.warn for error PDPs, debug line shows error count

\[✓\]new scanscan-url-v2 v7 — inserts free\_scans with status='scanning' before n8n call, updates to 'completed'/'error' after. Logs refund failures (was silent catch).

\[✓\]cureCleaned 22 stuck executions (oldest Feb 6) — marked as 'timeout' with legacy error message

\[✓\]cureCleaned 8 stuck purchased\_reports — marked as 'needs\_rerun'

\[✓\]cureBackfilled 7 free\_scans with status='completed', roast\_status='completed'

\[✓\]upgradeFull system architecture doc saved to Obsidian vault (Architecture/system-architecture.md)

\[✓\]upgradeMEMORY.md updated — fixed 6 wrong/outdated claims (root rules, X-RAY bug files, Obsidian counts, git autopush repos, failure references)

\[✓\]upgradeFile cleanup — archived Jan/Feb framer-overrides, copied shared components from admin-page/ to shared/, fresh Framer backup (2026-03-21-live)

2026-03-20

// Admin Page — Architecture Fix

\[✓\]cureIndexImportProvider v1.1.1 — removed purchased\_reports inserts from auto-import. purchased\_reports tracks customer payments (Polar.sh), NOT admin import. Auto-import now only upserts pdp rows.

\[✓\]cureDB cleanup — deleted 15 fake purchased\_reports rows for mar-2026 created by v1.1.0 auto-import.

\[✓\]upgradeUpdated PLAN-2026-03-19.md and framer-admin SKILL.md to reflect correct architecture.

// Admin Page — UX Improvements

\[✓\]new scanRecurringOrderItemsList v1.3.8 — RUNNING badges now show ASIN number on hover, mouseleave reverts to "RUNNING". Admin can identify which ASIN is being analyzed.

\[✓\]new scanAdminPDPProvider v1.5.19 — auto-flags analyzed PDPs with alignment score < 40. Parses "X/100" format, writes \`flagged=true\` to DB on page load. Prevents bad analysis results from reaching customers.

// Cloudflare Worker — Amazon Image Proxy

\[✓\]new scanDeployed \`amazon-image-proxy.pokpok.workers.dev\` — proxies Amazon CDN image requests through Cloudflare to bypass TLS fingerprinting that blocks Node.js (EPROTO error in n8n).

\[✓\]updateRegistered \`pokpok.workers.dev\` subdomain on Cloudflare. Worker restricts to Amazon image domains only (m.media-amazon.com, images-na/eu/fe.ssl-images-amazon.com).

\[✓\]updateSource at \`workers/amazon-image-proxy/\`. Usage: \`https://amazon-image-proxy.pokpok.workers.dev/?url=<encoded-amazon-url>\`

2026-03-19

// POKPOK Index — Monthly Podcast

\[✓\]new scanGenerated first POKPOK Index podcast via NotebookLM — two-person deep dive discussing March 2026 monthly results (top 15 movers, 5 uncomfortable truths). Feynman style: provocative, straightforward, no jargon. 17m49s, 128kbps MP3.

\[✓\]updateSource: Supabase Storage \`index/monthly/latest.json\` (349 products scanned, 28-day period Feb 17 – Mar 18)

\[✓\]updateMP3 pushed to GitHub Pages: \`https://xclv-ai.github.io/pokpok-report/products/index/pokpok-index-march-2026.mp3\`

\[✓\]updateBackup at \`pokpok-ai/index/podcast/pokpok-index-march-2026.mp3\`

2026-03-17

// X-RAY Bug Fixes (B25, B26) + Share Improvements

\[✓\]cureB25 — YOUR SCORE button not clickable with mouse. Root cause: Space Invaders Framer container (position:absolute, z-index:1) blocked all clicks in display area. Fix: useEffect + mergedRef reaches up to Framer container and sets pointer-events:none + visibility:hidden when not scanning. (Overrides v1.11.9)

\[✓\]cureB26 — Dial label re-click toggled OFF unexpectedly. Removed toggle behavior — each zone now navigates to its state and stays. OFF is a dedicated zone (top-right). No double-click needed. (Overrides v1.11.9)

\[✓\]cureShare clipboard copy failed silently — navigator.clipboard.writeText() called after async captureScreenshot(), losing user gesture context. Moved to before any awaits. (Overrides v1.11.9)

\[✓\]cureShare text showed "unknown" domain — xrayData.url undefined. Now reads from window.\_\_POKPOK\_XRAY\_NAV\_\_.scanUrl. (Overrides v1.11.9)

\[✓\]upgradeSHARE\_OG\_BASE updated to xray.pokpok.ai custom domain (was xclv-ai.github.io/pokpok-report)

\[✓\]new scanxray.pokpok.ai → pokpok.ai/products/xray redirect (GitHub Pages custom domain)

// X-RAY Phase 3.2 — Native LinkedIn Share + Dynamic OG Cards

\[✓\]new scan\`share-og\` edge function v1 — serves dynamic OG HTML with per-scan title, description, and image. LinkedIn crawler gets proper og:tags; browsers get meta-refresh redirect to Framer page. Deployed with \`no-verify-jwt\`.

\[✓\]new scan\`generate-scorecard\` edge function v2 — added GET handler so the function URL works as \`og:image\` src (was POST-only). Fixed CTA URL from \`pokpok.ai/scan\` to \`pokpok.ai/products/xray\`.

\[✓\]new scan\`claim-share-bonus\` edge function v2 — \`SHARE\_BASE\_URL\` changed from Framer URL to \`share-og\` edge function URL. Share links now point to the OG proxy, not directly to Framer.

\[✓\]new scanSQL migration \`004\_screenshot\_url.sql\` — added \`screenshot\_url\` text column to \`free\_scans\`, RLS policy for user updates.

\[✓\]new scanSupabase Storage bucket \`xray-screenshots\` (public) — stores html-to-image captures for og:image cards.

\[✓\]new scanXrayOverrides v1.11.0 (local, awaiting Framer paste) — screenshot uploads to Supabase Storage after html-to-image capture. Native LinkedIn share dialog (\`linkedin.com/sharing/share-offsite\`) replaces custom preview overlay. Removed: showPreview state, preview overlay, handleConfirmPost, \_buildPreview, \_ledColor helper.

\[✓\]new scanXrayProvider v1.8.0 (local, awaiting Framer paste) — removed LinkedIn OAuth flow (LINKEDIN\_CLIENT\_ID, LINKEDIN\_REDIRECT\_URI, openLinkedInAuthPopup), removed \`linkedin\_post\` action handler, removed \`\_\_POKPOK\_LINKEDIN\_\_\` global. Share action unchanged.

\[✓\]upgradeB7 (LinkedIn share 502) and B16 (LinkedIn re-auth) now moot — no more custom LinkedIn API posting or OAuth needed.

\[✓\]cure\`share-og\` edge function v2 — LinkedIn "Cannot display preview" (B19). Root cause: \`meta http-equiv="refresh"\` made LinkedIn's crawler follow redirect before reading OG tags. Fix: replaced with \`<script>window.location.replace(url)</script>\` — crawlers don't execute JS (F030).

Backend fully deployed. Frontend files (XrayOverrides v1.11.0 + XrayProvider v1.8.0) awaiting user paste into Framer editor.