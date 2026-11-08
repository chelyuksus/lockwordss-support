# Privacy review — 2026-11-08

## Decision
BLOCKED for official policy publication. Do not remove the draft warning or enable Pages until source and build mapping are verified. Do not submit App Privacy Details from this draft.

## Evidence available
- Owner identifies Lockwordss 1.1 build 5, bundle com.local.LocalPasswords.
- Baseline archive: `LocalPasswords 2.zip`, uploaded 2026-11-07 02:49 UTC. It predates later Codex changes. Source was inspected read-only, never copied into this public repository.
- Baseline `Security/KeychainStore.swift`: generic-password items, UUID account key, `kSecAttrAccessibleWhenUnlockedThisDeviceOnly`, no synchronizable flag in base query.
- Baseline `Models/PasswordEntry.swift`: SwiftData fields serviceName, displayName, login, email, phone, website, note, hasPassword, isFavorite, createdAt, updatedAt.
- Baseline `Security/AppLockController.swift`: `LocalAuthentication.deviceOwnerAuthentication`, system fallback to device passcode.
- Baseline `Views/EntryEditorView.swift`: create/update/delete and local generator, Keychain/SwiftData rollback handling.
- Baseline README explicitly says no network APIs; newer owner description says icon network requests and encrypted attachments. This discrepancy proves the archive is insufficient for the current release.
- No current app repository was available through the connected GitHub inventory; the user's Mac was not listed as an available environment.

## Must verify in current source/build
1. Exact commit / source checksum corresponding to 1.1 (5), and whether latest Codex changes are in that build.
2. All URLSession/HTTP/SDK destinations, fallback icon services, website discovery and consent. Record fields transmitted, triggers, user controls, redirects, caching, retention and supplier policies. Do not state 'no data collected' without this analysis.
3. SwiftData CloudKit configuration and entitlements, backup exclusions, cache and log contents.
4. Attachment encryption algorithm/key storage/accessibility, deletion, thumbnails/temp files, EXIF handling and recovery on another device.
5. Camera and photo picker implementation and permission strings. Do not assume broad photo-library access.
6. Current Keychain attributes and migration semantics; reinstall is not guaranteed to erase Keychain. No promise that device backup restores device-bound secrets.
7. Whether an in-app link to policy exists. Code changes require a separate task.
8. Export/import, analytics/crash reporting, clipboard and external links, any third-party SDKs.
9. Support operator/contact and private channel. No invented email or future company name.

## Apple requirements (official sources checked 2026-11-08)
- Support URL is required and should lead to actual contact information: https://developer.apple.com/help/app-store-connect/reference/app-information/platform-version-information/
- Public privacy URL required: https://developer.apple.com/help/app-store-connect/reference/app-information/app-privacy/
- Policy also needs an accessible in-app link; describe data, purposes, third parties, retention/deletion and consent: https://developer.apple.com/app-store/review/guidelines/#privacy
- Privacy Details are a separate declaration. On-device-only processing is not collection; third-party collection/retention must be considered: https://developer.apple.com/app-store/app-privacy-details/
- Unlisted requires separate Apple approval; anybody with the link may obtain the app. Not a private-access control: https://developer.apple.com/support/unlisted-app-distribution/

GitHub Issues is not named by Apple as a guaranteed replacement for contact information. A dedicated support email remains an owner decision. Public Issues must never receive secrets or sensitive screenshots.

## Website
Only local HTML and CSS; no analytics code, JavaScript, cookies set by our code, external fonts or CDN assets. GitHub hosting and Issues still process technical requests under GitHub's policy; do not claim the host collects nothing.
