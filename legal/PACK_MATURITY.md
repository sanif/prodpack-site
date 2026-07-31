# Pack Maturity

ProdPack uses evidence-based maturity labels. A manifest loading successfully is
not the same as a generated application passing its runtime checks.

## Maturity levels

| Level | Meaning | Release promise |
| --- | --- | --- |
| Verified golden path | The complete preset is generated from bundled resources, backend dependencies are installed, migrations are applied to a fresh database, backend tests pass, and the frontend passes type-check, lint, and production build. | Supported in the closed paid beta for the tested composition. |
| Composition checked | Pack manifests, ownership, markers, dependency and capability contracts, presets, and representative generation paths pass automated validation. | Available for evaluation. Provider setup and the final combined application still require buyer verification. |
| External verification required | The pack produces deploy or vendor integration artifacts that cannot be proven without buyer-owned credentials and infrastructure. | Deploy-ready files only. ProdPack does not claim that the external service was provisioned or deployed. |

## Verified golden paths

These are the only complete preset compositions currently covered by the full
generated smoke matrix:

| Preset | Auth path | Automated evidence |
| --- | --- | --- |
| SaaS MVP | Password JWT auth | Fresh migration, backend tests, frontend type-check, lint, and production build |
| Ecommerce Store | Password JWT auth | Fresh migration, backend tests, frontend type-check, lint, and production build |
| Supabase SaaS | Supabase JWT auth | Fresh migration, backend tests, frontend type-check, lint, and production build |

The CI command is:

```sh
GENERATED_SMOKE_FULL=1 cargo test --manifest-path src-tauri/Cargo.toml --test generated_smoke -- --ignored --nocapture --test-threads=1
```

Running with one test thread is intentional. Each case installs and builds a
complete generated repository, and parallel package-manager builds can contend
for CPU and memory on CI runners.

## Composition-checked catalog

Every bundled pack is covered by registry loading, protocol validation, preset
satisfiability, static generated-output checks, or a combination of those gates.
Packs outside the three presets above remain composition checked until a full
preset smoke includes them.

Current packs outside the verified golden paths:

- ai-chat
- calendar
- cloudflare-turnstile
- cms
- database-docker
- database-railway
- deploy-aws-pipeline
- design-grill
- design-system
- editable-content
- editable-content-supabase
- feature-flags
- git
- legal-docs
- newsletter
- notifications
- oauth
- payments-lemonsqueezy
- payments-paddle
- payments-paypal
- payments-razorpay
- rate-limiting
- release-pipeline
- storage-s3

## External verification boundary

The following pack families always require buyer-owned credentials or
infrastructure before their final behavior can be verified:

- Hosting and deployment: deploy-docker, deploy-aws, deploy-aws-pipeline,
  Railway, Vercel, database-docker, database-railway, and database-supabase
- Payments: Stripe, Paddle, PayPal, Razorpay, and Lemon Squeezy
- External services: Supabase, PostHog, Sentry, S3, email providers, OAuth
  providers, and Cloudflare Turnstile

Automated checks validate generated configuration shape, application builds,
local migrations, mocks, and tests. They do not create cloud resources, confirm
DNS, process a live payment, or prove production credentials.

## Promotion rule

A preset may be promoted to a verified golden path only when its generated
repository passes the automated gates below. Presets with `deploy-docker` must
also pass Compose validation and both image builds on a Docker-capable release
machine; that container gate is manual until the CI fleet includes Docker.

1. Clean generation from bundled resources.
2. Fresh dependency installation with zero known high-severity dependency audit findings.
3. Alembic upgrade to all heads on a fresh database.
4. Backend lint, app-focused type-check, and test suite.
5. Frontend audit, type-check, lint, and production build.
6. Docker image build and Compose configuration validation in release verification when Docker is included.
7. Authorization regression tests for every privileged route in the composition.

Pack version changes that alter generated runtime behavior must update the pack
changelog and re-run every verified preset containing that pack.
