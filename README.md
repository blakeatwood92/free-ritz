# Free Ripz

A standalone, mobile-first Next.js website for free trading card packs and mystery box signup promotions. Intended to be hosted in a **new GitHub repository and a separate Vercel project** from Rip & Ship.

## Start locally

```bash
npm install
npm run dev
```

## Deploy

1. Create a **new** GitHub repository called `free-ripz` and upload the extracted project files (with `package.json` at the repository root).
2. Import that repository into a **new** Vercel project; use the Next.js preset.
3. Set `NEXT_PUBLIC_SITE_URL` to your actual new domain (no domain is presumed owned).
4. Set `NEXT_PUBLIC_CONTACT_EMAIL` to your real website contact address before launch.
5. Deploy and check `/`, `/offers/tilt-rips-free-pack`, `/about`, `/submit`, `/privacy`, `/terms`, `/sitemap.xml`.

## Editing offers

Edit `lib/offers.ts`. Each offer includes a platform, headline, claim URL, code, requirements, terms link, last checked, and `noPurchase` flag. The listings, filters, and offer detail pages update automatically. This is a simple source-file content system; there is **no admin dashboard/database** in this initial version.

## Offer included

- **Tilt Rips:** user-provided code `TYMBSX`. Tilt Rips officially states that its current sign-up free pack is based on new-account app/phone/device verification, no purchase required; the referral code provides attribution. The exact reward and eligibility vary. Official information: https://tiltrips.com/support/faq/bonuses-promotions/how-do-referral-packs-work-for-the-new-user/ and https://tiltrips.com/support/faq/bonuses-promotions/what-are-the-typical-requirements-for-free-pack-codes/

Other platforms are intentionally **not shown as having free packs** without sufficient current evidence. Never represent an affiliate's own earning milestones (e.g. ClutchPacks $500 or RIP.FUN's free Starter spin for referrers) as customer free-pack offers.

## Before production launch

- Confirm domain, contact email, and operational/business information.
- Review legal and privacy templates for your jurisdiction and analytics setup.
- Test eligibility and current offer on the third-party site.
- Add a real custom logo/OG preview if desired, and consider hosting brand assets locally rather than loading favicons externally.
- Test production build. Link to third-party platforms may earn referral value and should retain disclosures.

## Gold design update (October 2026)

- Desktop hero includes a featured reward spotlight and layered pack artwork.
- Gold-gradient CTA buttons with shimmer on hover, keyboard focus, and reduced-motion support.
- Offer grid adapts from three desktop columns to two tablet columns and one mobile column.
- Promo-code copy controls, individual offer pages, and source attribution remain intact.
- This package was not fully production-build tested because dependency installation did not complete in the build environment. Run `npm install && npm run build` locally or inspect the first Vercel build logs.

## Platform logos

Desktop offer cards, featured offers, and individual offer pages now use a single `PlatformLogo` component. To bundle a verified official logo, put a PNG into `public/logos/` using its offer slug (currently `tilt-rips-free-pack.png`). Until then the site attempts the site's publicly served favicon, then a clean text fallback. Official PNG logos are not included in this archive.

## No-deposit-first homepage (October 2026 update)
The offer directory now defaults to **No Deposit Required** and sorts eligible no-purchase offers first. A prominent gold no-deposit banner appears above filters on desktop and mobile; visitors can choose **View all offers** to see purchase-required promotions too. Offer eligibility is based on the `noPurchase` field in `lib/offers.ts`; do not set this field true merely because a platform has an affiliate link.
