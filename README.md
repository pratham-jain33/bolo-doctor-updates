# Bolo Doctor — Android downloads

This repository holds the signed Android build of Bolo Doctor. It exists for one reason: there is no Play Store listing, so a doctor who is sent the app needs a link that still works three weeks later. The source is not here.

Page: https://pratham-jain33.github.io/bolo-doctor-updates/

## Latest

| | |
|---|---|
| Version | 0.12.1 (versionCode 21) |
| File | `bolo-doctor.apk` |
| Size | 13 MB |
| Requires | Android 8.0 (API 26) or newer |
| Direct link | https://github.com/pratham-jain33/bolo-doctor-updates/releases/latest/download/bolo-doctor.apk |

## What this is

A voice note app for solo doctors in small private clinics. The doctor speaks after a consultation in Hindi, Kannada, Hinglish or English. The app writes an English note, which the doctor reviews, edits and approves. Nothing is saved until it is approved.

## What this is not

- Not on the Play Store. This is a pre-release build installed outside the store.
- Not validated, not tested by doctors, not used by anyone yet.
- Not accurate by default. It is a draft the doctor corrects.
- Not a medical device and not a replacement for existing records.
- Not open source. This is a private build.
- Not supported. There is no help desk.

## What it needs

The app has no servers and ships no keys. The doctor brings two free API keys of his own:

- **Sarvam** — speech to text
- **Groq** — text to structured note

He pays those two providers directly, roughly one rupee per dictation visit. Neither account has required a card as of 1 November 2026, but that is their decision and it can change.

Patient data stays on the device. Notes are stored locally. API keys are encrypted on the device and are never backed up.

## Install

1. Open the link on the Android phone, in Chrome.
2. Download the file.
3. Open it. Android will ask to allow installs from this source. Allow it.
4. Install, then open the app and follow the setup guide.

## For the maintainer

Publishing a new build:

```bash
gh release create v0.12.1 bolo-doctor.apk \
  --repo pratham-jain33/bolo-doctor-updates \
  --title "Bolo Doctor 0.12.1" \
  --notes "Pre-release."
```

The asset must be named `bolo-doctor.apk` in every release so the `/releases/latest/download/bolo-doctor.apk` link never changes. Rename the build output before uploading.

Build note: the 0.12.1 asset here is the debug-signed build from `Bolo-android`. It installs and runs identically but is larger and not minified. Replace it with a release-signed build when a keystore is available, keeping the same version and asset name.
