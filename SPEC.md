# Lesson 01 specification

## STUDIO-001 · Launch a tested calculator on an existing server

**Status:** New calculator deployment verified; learner-summary review and GitHub PR/CI completion remain pending.
**Public calculator:** [https://calc.xenoshin.com](https://calc.xenoshin.com)
**Lesson issue:** [#1](https://github.com/pb392/my-server-studio/issues/1)
**Feature branch:** `studio-001-calculator`

## Agreed result

Add one supplied, fixed calculator image to the existing `hosting-web` Docker network and Traefik HTTPS setup. Preserve the existing production site, QA site, Traefik and WUD updater. No application features, replacement proxy, updater installation, server upgrade or fresh-server setup.

The learner agreed to the proposed hostname by adding its DNS record, then privately authenticated and ran the prepared doctor and launch commands. Doctor reported `ready`, `launch-new` and four existing containers. This was a **new launch**, not adoption: the existing production/QA containers use the learner's own images, while the new lesson container uses the supplied release.

The exact image and source commit are defined in [calculator-release.json](studio/calculator-release.json):

- Image: `docker.io/kaw393939/is373_ci_cd@sha256:aec414c990a5de6ed74c9e8dcb105b78f6358c03a8cea70a9d40dcda51c3a8fa`
- Source commit: `4600202bad42da0c5ffb11d83ce8364671293d3d`
- [Release source](https://github.com/kaw393939/is373_ci_cd/tree/4600202bad42da0c5ffb11d83ce8364671293d3d)
- [Supplied publication evidence](https://github.com/kaw393939/is373_ci_cd/actions/runs/36904255716)

No claim is made that this is the learner's build, a new application CI/CD pipeline or a vulnerability-free image. The supplied UI mentions automatic deployment; this lesson deliberately uses a fixed image.

## Actual evidence

The original successful new-launch report is preserved in [studio/evidence.json](studio/evidence.json), exported with the prepared allowlist. It records October 29, 2026 at 17:42:53 UTC (1:42:53 p.m. America/New_York). It is a dated observation, not continuous monitoring.

| Evidence | Actual result / link |
|---|---|
| Local prepared checks | Python 3.12 setup completed. `check --fast`: Black and Pylint passed; 91 tests passed and 2 E2E tests were deselected. Local Docker was unavailable, so no local Docker E2E pass is claimed. |
| Initial CI | [Template-copy CI run](https://github.com/pb392/my-server-studio/actions/runs/40919263547): `studio`, `validate` and `integration-contract` passed. Final PR CI remains pending and will be linked separately. |
| Runtime and public API | [Sanitized launch evidence](studio/evidence.json): expected image/commit and production health matched; trusted HTTPS passed; multiplication returned HTTP 200 and 42; division by zero returned 400; numeric string input returned 422. |
| Existing services | [Preservation evidence](studio/evidence.json): four existing containers unchanged in identity, state and published ports. Production https://xenoshin.com and QA https://qa.xenoshin.com returned HTTP 200 with trusted TLS both before and after launch. This does not certify every function of those services. |
| AI browser checks | On the public calculator, `6 × 7` showed browser 42, API 42 and “Results match”; `6 ÷ 0` showed “Cannot divide by zero.” and no result match. [Multiplication screenshot](studio/ai-browser-multiply.jpg), [invalid-input screenshot](studio/ai-browser-invalid.jpg). These are AI observations, separate from the learner's. |
| Learner contributions and assistance | [LEARNING.md](LEARNING.md); accuracy review and detailed learner browser/keep observations remain pending. |
| PR, final CI, merge and issue closure | Pending. [Lesson issue #1](https://github.com/pb392/my-server-studio/issues/1). |

## Remaining publication work and limits

Review the AI-drafted learning summary before publishing its excerpts. GitHub SSH access was enabled with the learner's approval using the existing Mac public key, scoped to this repository. SSH fetch succeeded; the private key stayed on the Mac. Initial file retrieval used HTTPS while SSH access was repaired. Link the actual PR and its full CI result, merge to `main`, and verify issue closure and the checks on `main`.

Private SSH settings, sudo authentication, raw runtime output and initial-launch backup stay outside Git in ignored local state. The public JSON is the prepared sanitized export. Passing CI, a published image, runtime metadata, browser observations and the learner's explanations establish different claims. A green status does not certify authorship, understanding or whole-server security.

## Optional instructor history

The records below are background, not steps to repeat. Their original anchors
remain here so earlier links continue to work.

## HOST-001 · Keep the Traefik dashboard private

[Historical requirement and evidence](book/changes/hosting-spec-history.md#host-001--keep-the-traefik-dashboard-private).

## HOST-002 · Controlled host maintenance

[Historical requirement and evidence](book/changes/hosting-spec-history.md#host-002--controlled-host-maintenance).

## HOST-003 · Companion image security maintenance

[Historical requirement and evidence](book/changes/hosting-spec-history.md#host-003--companion-image-security-maintenance).
