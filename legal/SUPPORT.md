# Closed Beta Support Policy

Effective date: July 30, 2026

## Included support

Paid-beta support covers:

- installation and launch of the signed ProdPack macOS app;
- catalog, selection, review, generation, and safe-overwrite defects;
- reproduction of failures in an unmodified verified golden path;
- clarification of generated setup and deployment documentation;
- access to signed updates released during the buyer's 12-month update period;
  and
- security-report coordination under `SECURITY.md`.

Send support requests to <support@prodpack.dev> from the purchase email.

## Supported systems

The closed-beta desktop target is macOS 12 or later on an Intel or Apple silicon
Mac. Releases are distributed as signed, notarized universal DMGs. Generated
project setup and deployment tools, including Docker, Bun, Python, Git, and
provider CLIs, have separate requirements documented in the generated repo.

The order confirmation must identify the supported desktop target. A future
change to this matrix applies only to later releases and does not remove access
to a buyer's last eligible compatible version.

## Response target

ProdPack aims to acknowledge beta support requests within three business days.
Priority is based on severity and reproducibility. The beta does not include an
uptime or response-time service-level agreement.

## What to include

- ProdPack version and macOS version;
- selected preset and packs;
- the failing step and exact error text;
- whether the generated repository was modified;
- a minimal reproduction with secrets removed; and
- relevant local tool versions, such as Bun, Python, Docker, and Git.

Do not send production secrets, private keys, full customer datasets, or payment
card data.

## Not included

Standard beta support does not include:

- custom application features or design work;
- operating the buyer's AWS, Supabase, Stripe, DNS, email, or other provider
  account;
- debugging changes made after generation unless separately agreed;
- data migration from an unrelated application;
- legal, privacy, tax, accessibility, or regulatory advice;
- emergency on-call coverage; or
- guaranteed support for packs outside the maturity boundary in
  `PACK_MATURITY.md`.

Paid implementation or design-partner work may be scoped separately in writing.

## Update eligibility

The purchase includes versions released during the 12 months after purchase.
The last eligible version remains usable after that period. Later updates or
support may require a new purchase or renewal, but no renewal is automatic.
