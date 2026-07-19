# Project Snapshot: KshemaLIC.in

This document is a complete state-recovery snapshot for `kshemalic.in`. If all context or chat history is lost, paste the contents of this file into a new conversation to resume work seamlessly.

---

## 1. Project Identity

- **Site Name:** `KshemaLIC` (English) / `ಕ್ಷೇಮ LIC (KshemaLIC)` (Kannada)
- **Domain:** `kshemalic.in`
- **Cloudflare Pages URL:** `https://kshemalic.pages.dev`
- **Custom Domain Status:** Pending DNS setup & Cloudflare Pages mapping.
- **Tech Stack & Versions:**
  - **Framework:** Astro (`^7.0.8`)
  - **Styling:** Tailwind CSS (`^4.3.2`) with `@tailwindcss/vite` (`^4.3.2`)
  - **Integrations:** `@astrojs/mdx` (`^7.0.3`) for MDX blog posts and `@astrojs/check` (`^0.9.9`)
  - **Platform Adapters:** `@astrojs/cloudflare` (`^14.1.3`)
  - **Linter/Compiler:** TypeScript (`^6.0.3`)
  - **Runtime Engine:** Node.js (`>=22.12.0`)
- **Design System Summary:**
  - **Colors (Tailwind 4 & CSS custom properties):**
    - **Canvas (Default floor):** `#000000` (Dark) / `#ffffff` (Light)
    - **Ink (Text/Heading):** `#ffffff` (Dark) / `#000000` (Light)
    - **Body text:** `#bbbbbb` (Dark) / `#444444` (Light)
    - **Body text (Strong):** `#e6e6e6` (Dark) / `#111111` (Light)
    - **Muted text:** `#7e7e7e` (Dark) / `#888888` (Light)
    - **Hairlines/Dividers:** `#2a2a2a` (Dark) / `#e2e8f0` (Light)
    - **Hairlines (Strong):** `#1f1f1f` (Dark) / `#cbd5e1` (Light)
    - **Surface Card:** `#0d0d0d` (Dark) / `#f8fafc` (Light)
    - **Surface Soft:** `#080808` (Dark) / `#f1f5f9` (Light)
    - **Surface Elevated:** `#161616` (Dark) / `#e2e8f0` (Light)
    - **Motorsport Brand Accent Stripe:** Light Blue (`#0066b1`) → Dark Blue (`#1c69d4`) → Red (`#e22718`)
  - **Font Stack:** `"Inter", "Noto Sans Kannada", sans-serif` for display/body. Integrates Latin display text with Noto Sans Kannada script.
  - **Zero-Radius / Uppercase Rules:**
    - Buttons, inputs, and cards use `border-radius: 0px` (flat sharp corners) to convey precision.
    - Uppercase is strictly restricted to navigation links, buttons, category labels, and display titles (with `1.5px` tracking).
    - Running copy (paragraphs, list items, articles) remains sentence-case, with explicit CSS resets to prevent uppercase inheritance.
- **Design System Location:** Detailed in [DESIGN.md](file:///d:/Nasir/KshemaLIC.in/DESIGN.md) in the project root.

---

## 2. Full File Structure

Below is the complete tree layout under the `src/` directory and its purpose:

- **[src](file:///d:/Nasir/KshemaLIC.in/shining-series/src/)**
  - **[assets](file:///d:/Nasir/KshemaLIC.in/shining-series/src/assets/)** *(Empty directory for future localized graphic files)*
  - **[components](file:///d:/Nasir/KshemaLIC.in/shining-series/src/components/)**
    - [AgentContact.astro](file:///d:/Nasir/KshemaLIC.in/shining-series/src/components/AgentContact.astro) - Certified advisor contact card displaying Nasir's profile and custom WhatsApp click-to-chat links.
    - [DataChart.astro](file:///d:/Nasir/KshemaLIC.in/shining-series/src/components/DataChart.astro) - Client-side responsive charts (bar and donut SVGs) for visual metrics.
    - [Footer.astro](file:///d:/Nasir/KshemaLIC.in/shining-series/src/components/Footer.astro) - Locale-sensitive global footer containing disclaimer and regulatory text.
    - [LanguageSwitcher.astro](file:///d:/Nasir/KshemaLIC.in/shining-series/src/components/LanguageSwitcher.astro) - Header link button translating pages (using translationId for cross-linked blog posts).
    - [MStripeDivider.astro](file:///d:/Nasir/KshemaLIC.in/shining-series/src/components/MStripeDivider.astro) - Motorsport accent divider carrying the tricolor logo stripe.
    - [Navbar.astro](file:///d:/Nasir/KshemaLIC.in/shining-series/src/components/Navbar.astro) - Global header bar containing brand logo, link menu, theme switcher, and language selector.
    - [Newsletter.astro](file:///d:/Nasir/KshemaLIC.in/shining-series/src/components/Newsletter.astro) - Subscription card capturing email/WhatsApp numbers for updates.
    - [ThemeToggle.astro](file:///d:/Nasir/KshemaLIC.in/shining-series/src/components/ThemeToggle.astro) - Control script toggling `.dark` class state on HTML element.
  - **[content](file:///d:/Nasir/KshemaLIC.in/shining-series/src/content/)**
    - **[blog](file:///d:/Nasir/KshemaLIC.in/shining-series/src/content/blog/)**
      - **[en](file:///d:/Nasir/KshemaLIC.in/shining-series/src/content/blog/en/)** *(12 English MD/MDX blog posts)*
      - **[kn](file:///d:/Nasir/KshemaLIC.in/shining-series/src/content/blog/kn/)** *(12 matching Kannada translations)*
    - [content.config.ts](file:///d:/Nasir/KshemaLIC.in/shining-series/src/content.config.ts) - Configures content loader and frontmatter validation schema for the blog collection.
  - **[layouts](file:///d:/Nasir/KshemaLIC.in/shining-series/src/layouts/)**
    - [Layout.astro](file:///d:/Nasir/KshemaLIC.in/shining-series/src/layouts/Layout.astro) - Core wrapper adding meta tags, canonical link, bilingual alternates, and body containers.
  - **[pages](file:///d:/Nasir/KshemaLIC.in/shining-series/src/pages/)**
    - [index.astro](file:///d:/Nasir/KshemaLIC.in/shining-series/src/pages/index.astro) - Homepage for English locale.
    - [why-choose-lic.astro](file:///d:/Nasir/KshemaLIC.in/shining-series/src/pages/why-choose-lic.astro) - Performance metrics landing page for English locale.
    - [rss.xml.ts](file:///d:/Nasir/KshemaLIC.in/shining-series/src/pages/rss.xml.ts) - Dynamic endpoint generating localized RSS feeds for posts.
    - [sitemap.xml.ts](file:///d:/Nasir/KshemaLIC.in/shining-series/src/pages/sitemap.xml.ts) - Dynamic sitemap generator providing proper bilingual alternates.
    - **[blog](file:///d:/Nasir/KshemaLIC.in/shining-series/src/pages/blog/)**
      - [index.astro](file:///d:/Nasir/KshemaLIC.in/shining-series/src/pages/blog/index.astro) - English blog listing, including search query index and categories tabs.
      - [[slug].astro](file:///d:/Nasir/KshemaLIC.in/shining-series/src/pages/blog/[slug].astro) - English post template rendering markdown content and details.
    - **[kn](file:///d:/Nasir/KshemaLIC.in/shining-series/src/pages/kn/)**
      - [index.astro](file:///d:/Nasir/KshemaLIC.in/shining-series/src/pages/kn/index.astro) - Localized Kannada homepage.
      - [why-choose-lic.astro](file:///d:/Nasir/KshemaLIC.in/shining-series/src/pages/kn/why-choose-lic.astro) - Localized Kannada performance metrics page.
      - **[blog](file:///d:/Nasir/KshemaLIC.in/shining-series/src/pages/kn/blog/)**
        - [index.astro](file:///d:/Nasir/KshemaLIC.in/shining-series/src/pages/kn/blog/index.astro) - Kannada blog listing with search and tags.
        - [[slug].astro](file:///d:/Nasir/KshemaLIC.in/shining-series/src/pages/kn/blog/[slug].astro) - Kannada post template mapping localized MD/MDX.
  - **[styles](file:///d:/Nasir/KshemaLIC.in/shining-series/src/styles/)**
    - [global.css](file:///d:/Nasir/KshemaLIC.in/shining-series/src/styles/global.css) - Core CSS definitions importing Tailwind and setting theme tokens.
  - **[utils](file:///d:/Nasir/KshemaLIC.in/shining-series/src/utils/)**
    - [i18n.ts](file:///d:/Nasir/KshemaLIC.in/shining-series/src/utils/i18n.ts) - Bilingual resource bundle definition and helper translation functions.

---

## 3. Routing & i18n Setup

- **Locale Configuration (`astro.config.mjs`):**
  ```javascript
  i18n: {
    defaultLocale: 'en',
    locales: ['en', 'kn'],
    routing: {
      prefixDefaultLocale: false
    }
  }
  ```
- **Locale Routing Rule:**
  - Default English routes are served unprefixed directly on root (e.g., `/` for homepage, `/blog/` for articles, `/why-choose-lic/` for performance landing page).
  - Kannada translation routes are prefixed with `/kn` (e.g., `/kn/`, `/kn/blog/`, `/kn/why-choose-lic/`).
- **Dynamic Post Cross-Linking:**
  - Blog post routing matches slug-to-slug using dynamic parameters: `/blog/[slug]/` for English and `/kn/blog/[slug]/` for Kannada.
  - The `LanguageSwitcher` fetches the active path. For blog posts, the template retrieves the counterpart translations via the `translationId` attribute. The template queries the content collection for the alternate language file having the matching `translationId`. It feeds this target URL (`counterpartUrl`) to the `LanguageSwitcher` component. If no counterpart translation exists, the button falls back to the index (`/blog/` or `/kn/blog/`).

---

## 4. Content Collection Schema

The blog schema inside [content.config.ts](file:///d:/Nasir/KshemaLIC.in/shining-series/src/content.config.ts) is configured as follows:

| Field | Type | Description |
|---|---|---|
| `title` | `z.string()` | Localized post title. |
| `description` | `z.string()` | Localized summary paragraph used for list cards and meta description SEO. |
| `date` | `z.coerce.date()` | Date parameter. Controls visibility (scheduled posts are only shown after this date). |
| `category` | `z.string()` | Post classification (e.g., `"Financial Planning"`, `"Policy Updates"`). |
| `tags` | `z.array(z.string())` | Array of strings for filter categories and indexing search matches. |
| `featuredImage` | `z.string().optional()` | Explicit static path to override automatically generated images. |
| `imageKeyword` | `z.string().optional()` | English keywords utilized by build pipeline to fetch relevant cover layouts from Pexels API. |
| `translationId` | `z.string()` | Non-localized ID mapping the English article to its corresponding Kannada counterpart. |
| `draft` | `z.boolean().optional()` | Boolean tag to flag unfinished entries. Defaults to `false`. |

---

## 5. Complete Blog Post Inventory

*Current Reference Date: July 19, 2026*
*Cadence: Scheduled posts are released systematically every 3 days.*

| Date | Translation ID | English Title | Kannada Title | Category | Draft | Status (as of July 19, 2026) |
|---|---|---|---|---|---|---|
| 2026-07-13 | `why-life-insurance-essential` | Why Life Insurance is Essential for Financial Security | ಆರ್ಥಿಕ ಭದ್ರತೆಗೆ ಜೀವ ವಿಮೆ ಏಕೆ ಅತ್ಯಗತ್ಯ? | Financial Planning | false | **Live** |
| 2026-07-20 | `future-policy-updates` | Future Policy Premium Term Adjustments | ಭವಿಷ್ಯದ ಪಾಲಿಸಿ ಪ್ರೀಮಿಯಂ ನಿಯಮಾವಳಿಗಳು | Policy Updates | false | **Scheduled** *(Tomorrow)* |
| 2026-07-23 | `lic-term-vs-endowment` | LIC Term Insurance vs Endowment: Which Plan Suits You Best? | ಎಲ್ಐಸಿ ಟರ್ಮ್ ಇನ್ಶೂರೆನ್ಸ್ vs ಎಂಡೋಮೆಂಟ್ ಪ್ಲಾನ್‌ಗಳು: ಯಾವುದು ಯಾರಿಗೆ ಸೂಕ್ತ? | Financial Planning | false | **Scheduled** |
| 2026-07-26 | `lic-premium-payment-grace-period` | LIC Premium Online Payment & Grace Period Rules Explained | ಎಲ್ಐಸಿ ಪ್ರೀಮಿಯಂ ಆನ್‌ಲೈನ್ ಪಾವತಿ ಮತ್ತು ಗ್ರೇಸ್ ಪಿರಿಯಡ್ ನಿಯಮಗಳ ವಿವರಣೆ | Financial Planning | false | **Scheduled** |
| 2026-07-29 | `lic-policy-loan-surrender-value` | Loan Against LIC Policy: How to Get a Policy Loan & Interest Rates Explained | ಎಲ್ಐಸಿ ಪಾಲಿಸಿ ಲೋನ್: ಸರೆಂಡರ್ ವ್ಯಾಲ್ಯೂ ಮೇಲೆ ಸಾಲ ಹೇಗೆ ಪಡೆಯಬಹುದು ಮತ್ತು ಬಡ್ಡಿ ದರ ವಿವರ | Financial Planning | false | **Scheduled** |
| 2026-08-01 | `lic-maturity-claim-process` | LIC Maturity Claim Process: Step-by-Step Document Checklist & Online Guide | ಎಲ್ಐಸಿ ಮೆಚುರಿಟಿ ಕ್ಲೈಮ್ ಪ್ರಕ್ರಿಯೆ: ಹಂತ-ಹಂತದ ದಾಖಲೆಗಳ ಪಟ್ಟಿ ಮತ್ತು ಆನ್‌ಲೈನ್ ಗೈಡ್ | Financial Planning | false | **Scheduled** |
| 2026-08-04 | `lic-death-claim-nominee` | LIC Death Claim Process for Nominee: Step-by-Step Form & Document Checklist | ಎಲ್ಐಸಿ ಮರಣ ಕ್ಲೈಮ್ ಪ್ರಕ್ರಿಯೆ: ನಾಮಿನಿಗಳಿಗೆ ಹಂತ-ಹಂತದ ಮಾರ್ಗದರ್ಶಿ ಮತ್ತು ದಾಖಲೆಗಳ ಪಟ್ಟಿ | Financial Planning | false | **Scheduled** |
| 2026-08-07 | `lic-policies-nri` | LIC Policies for NRIs: Indian Insurance Rules, Eligibility & Process | ನಿವಾಸಿ ರಹಿತ ಭಾರತೀಯರಿಗೆ (NRI) ಎಲ್ಐಸಿ ಪಾಲಿಸಿಗಳು: ನಿಯಮಗಳು ಮತ್ತು ತೆರಿಗೆ ಪ್ರಯೋಜನಗಳು | Financial Planning | false | **Scheduled** |
| 2026-08-10 | `lic-vs-ppf-vs-mutual-funds` | LIC vs PPF vs Mutual Fund: Which is the Best Long-Term Investment in India? | ಎಲ್ಐಸಿ vs ಪಿಪಿಎಫ್ vs ಮ್ಯೂಚುವಲ್ ಫಂಡ್: ದೀರ್ಘಾವಧಿ ಹೂಡಿಕೆಗೆ ಯಾವುದು ಅತ್ಯುತ್ತಮ? | Financial Planning | false | **Scheduled** |
| 2026-08-13 | `lic-bima-sakhi-yojana` | LIC Bima Sakhi Yojana: Eligibility, Registration & Scheme Benefits | ಎಲ್ಐಸಿ ಬಿಮಾ ಸಖಿ ಯೋಜನೆ: ಅರ್ಹತೆ, ನೋಂದಣಿ ಮತ್ತು ಯೋಜನೆಯ ಪ್ರಯೋಜನಗಳು | Financial Planning | false | **Scheduled** |
| 2026-08-16 | `lic-tax-saving-guide` | Section 80C & 10(10D): The Complete Tax-Saving Guide for LIC Premiums | ಸೆಕ್ಷನ್ 80C ಮತ್ತು 10(10D): ಎಲ್ಐಸಿ ಪ್ರೀಮಿಯಂ ಮೇಲಿನ ತೆರಿಗೆ ಉಳಿತಾಯದ ಸಂಪೂರ್ಣ ಮಾರ್ಗದರ್ಶಿ | Financial Planning | false | **Scheduled** |
| 2026-08-19 | `lic-policy-revival` | How to Revive Lapsed LIC Policy: Schemes, Process & Late Fees | ಲ್ಯಾಪ್ಸ್ ಆದ ಎಲ್ಐಸಿ ಪಾಲಿಸಿ ಪುನರುಜ್ಜೀವನಗೊಳಿಸುವುದು ಹೇಗೆ: ನಿಯಮಗಳು ಮತ್ತು ಬಡ್ಡಿ ವಿನಾಯಿತಿ | Financial Planning | false | **Scheduled** |

---

## 6. Verified Facts Registry

*Verbatim Reproduction of [CONTENT_PLAYBOOK.md](file:///d:/Nasir/KshemaLIC.in/CONTENT_PLAYBOOK.md):*

```markdown
# KshemaLIC Content Playbook

## Every blog post must:
- Be written in BOTH English (src/content/blog/en/) and Kannada (src/content/blog/kn/), sharing the same `translationId`
- Use frontmatter matching the existing schema: title, description, date, category, tags, translationId, draft, imageKeyword
- Set `date` to the next available slot, spaced according to the site's publishing cadence (every 2-3 days), based on the most recent existing post's date — never duplicate or backdate
- Include 1-2 relevant `imageKeyword` terms in English (for the Pexels API fetch pipeline) even though the post itself may be Kannada
- End with a natural transition sentence inviting the reader to consult a certified LIC agent — do NOT repeat the IRDAI disclaimer text in the body, it's already rendered by the page template

## Factual accuracy rules (non-negotiable):
- Section 80C combined deduction limit is ₹1,50,000 per financial year — never state any other figure
- Section 10(10D) tax-free maturity ALWAYS requires stating the condition (premium ≤10% of sum assured for policies after April 2012) — never state maturity is tax-free unconditionally
- NEVER claim ULIPs, Index Plus, or any market-linked plan offers "guaranteed returns" — these are market-linked and must state that returns fluctuate with market performance
- NEVER invent a specific report/table citation (e.g., "Table 1.15") unless you can verify it exists — when citing LIC's claim settlement ratio, AUM, or solvency ratio, use ONLY these pre-verified figures and do not alter them:
  - Claim Settlement Ratio: 98.15% (FY 2024-25, IRDAI data)
  - Assets Under Management: ₹57.29 Lakh Crore (March 2026)
  - Solvency Ratio: 2.35 (March 2026; IRDAI-mandated minimum is 1.5)
- NEVER make disparaging or fabricated claims about competing insurers (no invented limits, no unverifiable comparisons)
- If a figure is needed that isn't in this file and can't be verified from official sources (IRDAI, Income Tax Act, LIC Act, RBI), phrase the point generally instead of stating a specific number

## Data visualization:
- Whenever the post includes comparative percentages, allocation breakdowns, or year-over-year figures, use the `<DataChart>` component (donut for proportions/allocations, bar for comparisons/trends) instead of relying only on a text table
- Import DataChart in .mdx posts only (not supported in plain .md)

## Images:
- Do not embed images directly — the `imageKeyword` frontmatter field is used by the existing Pexels fetch pipeline to auto-attach a featured image at build time
```

---

## 7. Known Gaps / Not Yet Done

- **Agent Code and Registration Placeholders:** The variables `PUBLIC_AGENT_CODE` and `PUBLIC_IRDAI_REG` are currently configured in environment logic/Astro translation configs with fallback strings `[Agent Code Placeholder]` and `[IRDAI Code Placeholder]`. Real credentials need to be injected before launch.
- **OG-Image Status:** The reference `/og-image.jpg` exists in metadata templates inside `Layout.astro` as a placeholder fallback, but the actual file has not yet been designed or placed in the `/public/` asset folder.
- **Pexels API Integration:** The `imageKeyword` configuration fields exist on every article for build-time automated image attachment. The direct automated runner pipeline hook requires real environment credentials and active integration verification.
- **Custom Domain Attachment Status:** The custom domain `kshemalic.in` is registered and referenced in canonical links, XML sitemaps, and layout structures, but actual DNS delegation and Cloudflare Pages binding remain pending deployment completion.

---

## 8. Deployment Details

- **Cloudflare Pages Project Name:** `kshemalic`
- **Build Command:** `npm run build` (which maps to `npm run --prefix shining-series build` inside the root workspace configurations)
- **Build Output Directory:** `./shining-series/dist`
- **Deploy Trigger Type:** Manual deploy via Wrangler CLI (`npm run deploy` maps to `wrangler pages deploy` command targeting build folder), though it is prepared to transition to a Git-connected auto-deploy flow.
