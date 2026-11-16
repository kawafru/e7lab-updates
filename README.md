# E7Lab updates

Public update channel for E7Lab (에붕연구소). Application and Byblis source code remain private.

Current application version: **1.02b**. This portable build checks `latest.json` in the background at startup. A newer version opens a notice; clicking Update downloads, verifies, installs and restarts the app. The Data & Guide page also provides a manual check. No roster, match history, account, or credentials are sent. Checks are coalesced and cached for ten minutes; failures back off for one minute and never block local analysis.

## Publishing the next version

1. Set `APP_VERSION` in the private application source and add concise release notes.
2. Build and verify a clean portable ZIP with zero owned heroes, no UserData, and the Foundry exclusion preset included.
3. Publish a release here (for example `v1.02`) and attach the verified ZIP. Never upload source, personal caches, or credentials.
4. After the release is published and its digest verified, update `latest.json`: set the comparable `version`, optional `displayVersion`, release-page `downloadUrl`, `sha256` and concise user-facing `notes`. Letter suffixes use a numeric compatibility version, e.g. `1.02.0.2` with `displayVersion: 1.02b`. Do not advertise an unpublished release.
5. Verify the manifest anonymously and test an older client against it.

Version segments are compared numerically: 1.02 is newer than 1.01. Keeping a release at 1.01 does not prompt existing 1.01 users to update. Older ZIPs created before the update checker was added must be replaced once with this build. To upgrade, close the app, replace the application files, and keep the existing UserData folder. Extract into a new folder for a clean installation.

## Native updates since v1.02b

The new Update button downloads, verifies SHA-256, installs and restarts the desktop app, preserving UserData. Versions 1.01/1.02 need one manual replacement first. The numeric compatibility version 1.02.0.2 plus displayVersion 1.02b lets legacy numeric-only checkers detect this letter-suffix release. Always keep native and Node version ordering in sync. After verifying the release asset, publish its SHA-256 in latest.json. Never upload UserData or advertise unpublished assets.

The v1.02b portable asset includes the TLS 1.2 download fix. The superseded pre-fix asset is labeled `before-TLS-fix`; use `E7Lab-v1.02b.zip` for installation. Certificate validation stays enabled.
