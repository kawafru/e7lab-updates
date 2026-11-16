# E7Lab updates

Public update channel for E7Lab (에붕연구소). Application and Byblis source code remain private.

Current application version: **1.02**. This portable build checks `latest.json` in the background at startup. Newer versions open a download notice; files are not installed automatically. The Data & Guide page also provides a manual check. No roster, match history, account, or credentials are sent. Checks are coalesced and cached for ten minutes; failures back off for one minute and never block local analysis.

## Publishing the next version

1. Set `APP_VERSION` in the private application source and add concise release notes.
2. Build and verify a clean portable ZIP with zero owned heroes, no UserData, and the Foundry exclusion preset included.
3. Publish a release here (for example `v1.02`) and attach the verified ZIP. Never upload source, personal caches, or credentials.
4. After the release is published, update `latest.json`: set `version` to `1.02`, `downloadUrl` to the release page, and `notes` to a concise user-facing summary. Do not advertise an unpublished release.
5. Verify the manifest anonymously and test an older client against it.

Version segments are compared numerically: 1.02 is newer than 1.01. Keeping a release at 1.01 does not prompt existing 1.01 users to update. Older ZIPs created before the update checker was added must be replaced once with this build. To upgrade, close the app, replace the application files, and keep the existing UserData folder. Extract into a new folder for a clean installation.
