# Deployment status and procedure

## Status on 2026-11-08
- Repository `chelyuksus/lockwordss-support` created as PUBLIC, as explicitly requested.
- GitHub Issues is available as a public fallback.
- GitHub Pages has NOT been enabled. Current drafts are not official published pages.
- No changes to app code, Apple Developer/App Store Connect, other repositories or Hetzner.
- No paid resources or custom domain.

## Proposed URLs — NOT yet verified live
- Support: https://chelyuksus.github.io/lockwordss-support/
- Privacy: https://chelyuksus.github.io/lockwordss-support/privacy.html

## Publication gate
Complete PRIVACY_REVIEW.md against current build source. Replace uncertainty placeholders with verified statements, confirm contact mechanism, remove DRAFT warning and noindex only after review. Record source commit/checksum and date without publishing source code or secrets.

## Enable Pages after the gate
Use Settings → Pages → Deploy from a branch → main → /(root). This is a static HTML/CSS site; no paid infrastructure or custom Actions workflow is needed. Enforce HTTPS if the setting is available. Wait for the Pages deployment to report success; a Git commit alone is not publication.

## End-to-end verification
1. Open both canonical HTTPS URLs without authentication; require successful responses and correct content.
2. Check iPhone, iPad, desktop layouts, light/dark themes, keyboard focus, text zoom and no horizontal overflow.
3. Check navigation, public Issues link and official policy links.
4. Verify no secret/personal data and no external scripts, fonts or analytics.
5. Record deployed commit and observed URLs, not expected URLs.
6. Deliver the two verified URLs to the owner for Support URL and Privacy Policy URL.
7. Do not fill App Privacy Details, submit for review or request Unlisted as part of this task.
