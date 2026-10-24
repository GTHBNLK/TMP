# Remaining differences: test page `paps-clean` vs original live page

**Live (original):** `www.mintassetmanagement.com/promo/2026/year-end/paps`, published 13 Oct 2026, 13:01 UTC.  
**Test:** `/promo/2026/year-end/paps-clean` on the test site, published 22 Oct 2026, 10:02 UTC.  
**Checked on:** 22 Oct 2026. Sections 4 and 6 were updated on 24 Oct 2026. The rest was last checked on 22 Oct.

**Everything not listed here matches,** except the five client text changes recorded in `native-ad-page-text-changes.md`. On 22 Oct all 35 text blocks, including the disclosures, were identical before those changes.

**Main-site copy:** the page "PAPS-Native" (`/promo/2026/paps-native`) was published on 23 Oct 2026 behind the temporary password. Its form already has the final name "Order Form New", the field names and the placeholders, so section 1 applies only to the test page.

---

## 1. Form field names and placeholders

1. **Form name:**
   1. Test page: "Email Form 2".
   2. Live page: "Order Form New".
2. **Field names:**
   1. Test page: "Field", "Field 2", "Field 3", "Field 4".
   2. Live page: "First Name", "Last Name", "Email", "Phone".
3. **Placeholders:**
   1. Test page: "Example Text" in all four fields.
   2. Live page: "First Name", "Last Name", "Email", "Phone".
4. This is the manual Designer fix you planned to do.

## 2. Heading id

1. **Test page:** `y28-request-title`.
2. **Live page:** `y27-request-title`.
3. The test page uses the new `y28` prefix on purpose.

## 3. Images

1. **Logo and author photo on the test page:** local assets, as you asked.
2. **On the live page:** its own logo file, and an author photo hosted on Google.

## 4. Bot protection (corrected 23 Oct 2026)

1. **No difference.** Cloudflare Turnstile is a site-level setting, so every Webflow form on the site carries the same site key.
2. **Checked on 23 Oct 2026:** 51 published promo pages. Every page with a form, including the test page and the new `paps-native` page, has the key on its `<form>` tag.
3. **Why this was listed before:** the saved copy of the live page had been captured after the widget loaded, so it looked different. That was a capture difference, not a missing setting.
4. **Not checked:** the visible widget, because Webflow's script adds it at page load. A real test submission on `paps-native` worked.

## 5. Head scripts

1. **Live page:** loads its tracking scripts, for example Intellimize.
2. **Test page:** does not load them yet.

## 6. Extra elements on the test page (kept on purpose)

1. **Removed on 23-24 Oct 2026:**
   1. The map animation keyframes, when the map became the site's world map image.
   2. The reduced-motion embed for the form button, on both sites. The button's hover only changes the text colour, and the transition covers background and border colour, so the rule had no visible effect.
2. **A plain `div` wrapper:** Webflow adds one around the disclosures code embed. It will go when the disclosures are rebuilt as normal elements (planned).
3. **A `span`** around the last line of the author role ("Bryan Perry's Private Clients"). It is the only way to put text after the line break with the available tools, and removing it would delete that line.
4. None of them has a visual effect or a validation problem, so they are left in place.

## 7. Edits to the previous promo (24 Oct 2026, draft until published)

1. **Where:** the shared component "Promo: 2026 Year-End", used by all five variations (paps, peps, pafas, parw, pasi). One edit covers all five.
2. **Author photo:** both the link and the image now point to our hosted image instead of the Google-hosted one.
3. **Stray Turnstile input:** the `cf-turnstile-response` hidden input is removed. It was copied into the page's code from a rendered page and did nothing.
4. **Not touched:** the empty `<template>` that holds a leftover Turnstile iframe stays. Webflow's own Turnstile setup on the form is unchanged.
5. **Check after publishing:** compare the published HTML with the 11:30 UTC copy. Only these two changes should differ.

## 8. Added after the comparison (24 Oct 2026)

1. **Map background:** the native page uses the site's `world-map-background` class plus a `claude-map-y28` combo (multiply blend, scrolling instead of fixed at tablet width and below). The live page has no map layer of this kind.
2. **Hero and content card:** their backgrounds are `#ffffffcc` and `#ffffffdd`, so the map shows through softly.
3. **Form block:** the form uses `contact_form` + `claude-form-body` (one column, flexbox) and inputs with `claude-form-input`. Barlow is not set on the inputs because they inherit it from the body.
