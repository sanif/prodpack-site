# Security Policy

## Supported versions

During the closed paid beta, security fixes are provided for the latest signed
ProdPack release. A purchaser receives releases published during the 12 months
after purchase. Generated repositories remain buyer-owned, but ProdPack cannot
maintain or secure buyer modifications after generation.

| Product | Security support |
| --- | --- |
| Latest signed beta release | Supported |
| Earlier beta releases | Update to the latest release before requesting a fix |
| Generated golden paths | Reproduction supported against the unmodified generated output |
| Modified generated repositories | Best-effort triage; buyer owns remediation after modification |
| Packs labeled Composition checked or External verification required | Scope is stated in `PACK_MATURITY.md` |

## Reporting a vulnerability

Send a private report to <security@prodpack.dev>. Do not open a public issue for a
suspected vulnerability.

Include, when possible:

- affected ProdPack and pack versions;
- whether the issue is in the desktop app or generated output;
- minimal reproduction steps;
- impact and attack preconditions;
- logs or sample files with secrets removed; and
- whether the issue is already public or actively exploited.

Do not include production credentials, customer data, private keys, payment
card data, or a full proprietary repository. ProdPack will provide a secure
transfer method if additional material is required.

## Response targets

These are targets for the closed beta, not a guaranteed service-level agreement:

- acknowledge a complete report within three business days;
- provide an initial severity assessment within seven business days;
- prioritize a fix or mitigation for confirmed critical issues; and
- coordinate disclosure after a fix is available when the reporter cooperates.

## Safe-harbor expectations

Good-faith research that avoids privacy violations, service disruption,
extortion, social engineering, and access to data beyond what is needed to
confirm the issue will not be pursued by ProdPack solely because it revealed a
vulnerability. This statement does not authorize testing third-party services
or buyer deployments.

## Security boundary

ProdPack verifies only the behaviors documented in `PACK_MATURITY.md`. Buyers
remain responsible for production secrets, provider accounts, infrastructure,
DNS, monitoring, backups, legal compliance, dependency maintenance after the
included update period, and review of generated code before deployment.

The desktop app has no ProdPack telemetry or cloud control plane. Dependency
installs, provider CLIs, and generated applications may communicate directly
with their respective third-party services.
