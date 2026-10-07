# AumNote OTA

Public distribution repository for **web-runtime OTA bundles only**.

Canonical rules:

- The Android application and source of truth live in the private `shifmana1987-ui/AumNote` repository.
- This repository must never become a second AumNote source tree.
- This repository must not contain APK files, signing keys, passwords, tokens, or source secrets.
- The installed native shell family is selected by `latest.json.nativeVersionCode`.
- Web-only updates are stored under `bundles/` and verified by SHA-256 before activation.
- A native Android change requires a new signed canonical base APK from the main AumNote repository; it is **not** shipped as OTA.
- Keep `latest.json.enabled=false` until a bundle has passed the canonical device acceptance gate.

Current native family: **450**.

Owner-acceptance delivery order:

`AumNote/candidate/owner -> OTA bundle -> owner's phone -> OWNER OK -> AumNote/main`

OTA is therefore a **pre-merge owner-testing transport**, not a post-`main`
deployment step. A failed candidate never changes `main`.

