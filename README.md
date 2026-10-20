# WODS-I Scanner QA Updates

Public distribution channel for **WODS-I Scanner QA Android APKs only**.

The application source code remains private in `Shasmeer/WODS-I`.
This repository must **never** contain Angel One API credentials, broker session
tokens, Supabase service keys, signing keystores, investment/portfolio details,
private datasets, or internal configuration.

## Release process

A protected, manually approved build in the private WODS-I repository produces:

- `WODS-I-Scanner-QA.apk` — permanently signed QA APK.
- `latest-qa.json` — release metadata including package ID, version code,
  APK size, APK SHA-256, and signing certificate SHA-256.

After verifying the APK on Android, publish the APK as a GitHub Release asset
named `WODS-I-Scanner-QA.apk` with tag `vX.Y.Z-qa`, and then publish
`latest-qa.json` to this repository's **main** branch.

The app's update check reads
`https://raw.githubusercontent.com/Shasmeer/WODS-I-Update/main/latest-qa.json`.

**No APK or live update manifest has been published yet.**
Do not create a fake manifest or a release without a verified, permanently
signed APK. An installed APK can be upgraded only when both builds have
the same Android package ID and signing certificate, with a newer version code.

The QA app uses sample market data. It is not a production trading application.
