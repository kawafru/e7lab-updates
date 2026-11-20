# E7Lab updates

Public update channel for E7Lab (에붕연구소). Application and Byblis source code remain private.

Current application version: **1.05**. This portable build checks `latest.json` in the background at startup. A newer version opens a notice; clicking Update downloads, verifies, installs and restarts the app. The Data & Guide page also provides a manual check. No roster, match history, account, or credentials are sent. Checks are coalesced and cached for ten minutes; failures back off for one minute and never block local analysis.

## Publishing the next version

1. Set `APP_VERSION` in the private application source and add concise release notes.
2. Build and verify a clean portable ZIP with zero owned heroes, no UserData, and the Foundry exclusion preset included.
3. Publish a release here (for example `v1.02`) and attach the verified ZIP. Never upload source, personal caches, or credentials.
4. After the release is published and its digest verified, update `latest.json`: set the comparable `version`, optional `displayVersion`, release-page `downloadUrl`, `sha256` and concise user-facing `notes`. Letter suffixes use a numeric compatibility version, e.g. `1.02.0.2` with `displayVersion: 1.02b`. Do not advertise an unpublished release.
5. Verify the manifest anonymously and test an older client against it.

Version segments are compared numerically: 1.02 is newer than 1.01. Keeping a release at 1.01 does not prompt existing 1.01 users to update. Older ZIPs created before the update checker was added must be replaced once with this build. To upgrade, close the app, replace the application files, and keep the existing UserData folder. Extract into a new folder for a clean installation.

## Native updates since v1.02b

The new Update button downloads, verifies SHA-256, installs and restarts the desktop app, preserving UserData. Versions 1.01/1.02 need one manual replacement first. The numeric compatibility version 1.02.0.2 plus displayVersion 1.02b lets legacy numeric-only checkers detect this letter-suffix release. Always keep native and Node version ordering in sync. After verifying the release asset, publish its SHA-256 in latest.json. Never upload UserData or advertise unpublished assets.

The v1.02b portable asset includes TLS 1.2 and reads the latest manifest through the GitHub Contents API when Update is clicked, avoiding stale raw-CDN validation hashes. Startup notices remain cached. Archives labeled `before-TLS-fix` or `before-cache-fix` are superseded; use `E7Lab-v1.02b.zip` for installation. Certificate validation stays enabled.


## Silent maintenance builds

The public app version can stay at v1.03 while installer builds advance numerically, starting with 1.03.0.1. `APP_VERSION` in the package is the installer identity; `APP_DISPLAY_VERSION` is the user-facing version. Publish `E7Lab-v1.03.0.1.zip` under tag `v1.03.0.1`, with the release title `v1.03`. The manifest uses `version: 1.03.0.1` and `appVersion: 1.03`; omit `displayVersion` for this scheme to preserve strict legacy validation. Keep `notes` empty for a silent patch and retain the existing in-app release-note history.

Old v1.03 startup checkers show the numeric build once because their schema has no separate public-version field. Existing native installers can still resolve and verify the build-tagged asset. Updated checkers display the public version, detect subsequent higher builds of that release, and stop notifying after the installed build matches. Never advertise a new build before verifying the published archive digest.


v1.04 adds four-plan draft evaluation and conditional stat-scaling/counter synergy. The portable asset starts with zero owned heroes and keeps the 20-hero Foundry preset. Native update verification covers v1.02b and v1.03 to v1.04, preserving UserData.


## v1.04b

This release prioritizes intrinsic stats and observed early-pick flexibility, adds local per-draft-stage estimates with explicit validation gates, analysis-history export/import and anonymized official Champion+ match collection. Current and previous regular-season statistics are combined without duplicate accumulation. The clean package contains zero owned heroes, no personal history or UserData, and the 20-hero Foundry exclusion preset. Visual verification was omitted at the owner’s request; automated and native update safety checks passed.

Compatibility identity: `version: 1.04.0.2`, `displayVersion: 1.04b`, with tag `v1.04b` and asset `E7Lab-v1.04b.zip`. Omit `appVersion` for this suffix scheme, so pre-existing v1.04 and earlier native clients resolve the same release and staged app identity correctly.


## v1.04c

Expand the public Champion+ corpus from 273 to 2,228 unique actual matches, using all top-100 ranking entries and deeper history pages. The final 4v4 and each pick phase retain their original chronological validation gates. The UI reports actual validation failures separately from insufficient samples. Clean installs start with zero owned heroes and the 20-hero Foundry preset. Source requests remain serialized and bounded; inference runs locally. Use wire identity `1.04.0.3` plus `displayVersion: 1.04c`, tag `v1.04c`, asset `E7Lab-v1.04c.zip`; omit `appVersion` for legacy suffix compatibility.


## v1.04d

Prioritize intrinsic strength/flexibility in the first two own picks, then reviewed mechanic counters against revealed opponents. Live opponent commentary explains conditional composition paths and responses without inferring private intent or unseen gear. Probability features remain separate and unchanged. Zero-owned portable package with the 20-hero Foundry preset. Wire identity `1.04.0.4`, displayVersion `1.04d`, tag `v1.04d`, asset `E7Lab-v1.04d.zip`.


## v1.05

Conditional draft recommendations use 36,851 sanitized unique actual BOTH-Champion+ Slendy matches, with sided prebans, pick side, revealed picks, second-side opening pairs and Vanguard usage. Mixed-tier side/slot, pair/trio and mover aggregates are supporting priors, clearly separated from exact contexts. Registered skill capabilities and the owned-ready pool inform concise opponent commentary. Detailed history preserves per-pick reasons, counts, bans and full commentary across JSON export/import, without recalculating old reasoning from new statistics.

The independent probability dataset remains 2,228 official actual-outcome games; recommendation counts are not silently added to probability training. The portable package starts with zero owned heroes, contains no personal UserData/history and retains the 20-hero Foundry preset. Existing native updates preserve UserData.

Manifest identity: `version: 1.05`; release tag `v1.05`; asset `E7Lab-v1.05.zip`. This numeric version requires no compatibility suffix alias. The approved review ZIP was promoted byte-for-byte, with its verified SHA-256 in latest.json.


### v1.05 maintenance build 1.05.0.1

The public version and in-app release-note list remain 1.05. The installer build is 1.05.0.1, using tag v1.05.0.1 and asset E7Lab-v1.05.0.1.zip. The manifest sets appVersion to 1.05, omits displayVersion and carries an empty notes field. Existing 1.05 installations detect this maintenance build once.

Live draft commentary now shows short revealed-mechanic and owned-ready-response lines without source counts. The conditional-statistics box is removed; full reasoning and evidence remain in frozen analysis history. Unconfirmed opponent continuation candidates appear in a compact list in the center readout. The release preserves UserData and the clean package retains zero owned heroes and the 20-hero Foundry preset.
