# Remaining differences: test page `paps-clean` vs original live page

**Live (original):** `www.mintassetmanagement.com/promo/2026/year-end/paps`, published 13 Oct 2026, 13:01 UTC.  
**Test:** `/promo/2026/year-end/paps-clean` on the test site, published 22 Oct 2026, 10:02 UTC.  
**Checked on:** 22 Oct 2026.

**Everything not listed here matches.** All 35 text blocks, including the disclosures, are identical on both pages.

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

## 4. Bot protection

1. **Live page:** the form has the Cloudflare Turnstile field.
2. **Test page:** the form has none yet.

## 5. Head scripts

1. **Live page:** loads its tracking scripts, for example Intellimize.
2. **Test page:** does not load them yet.

## 6. Extra elements on the test page (kept on purpose)

1. **Two plain `div` wrappers:** Webflow adds one around each code embed.
   1. One holds the map animation keyframes and the reduced-motion rules. Removing it would stop the map animation.
   2. One holds the disclosure paragraph with its line breaks. Removing it would mean rebuilding the disclosures.
2. **A `span`** around the last line of the author role ("Bryan Perry's Private Clients"). It is the only way to put text after the line break with the available tools, and removing it would delete that line.
3. None of them has a visual effect or a validation problem, so they are left in place.
