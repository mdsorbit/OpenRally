# Nitro Rush Android build

This repository produces an installable debug APK automatically with GitHub Actions.

## Build an APK

1. Open the repository's **Actions** tab.
2. Select **Nitro Rush Android Build**.
3. Press **Run workflow** on the `main` branch.
4. Wait for the workflow to finish.
5. Open the completed run and download the `nitro-rush-debug-apk` artifact.
6. Extract the ZIP and install `app-debug.apk` on an Android test device.

A debug APK is for testing only. It is not a Play Store release.

## Play Store AAB signing

A Play Store upload requires a release-signed Android App Bundle and a private signing key. Create or obtain a release keystore securely, then add these GitHub Actions repository secrets under **Settings → Secrets and variables → Actions**:

- `ANDROID_KEYSTORE_BASE64`: base64-encoded keystore file
- `ANDROID_KEYSTORE_PASSWORD`
- `ANDROID_KEY_ALIAS`
- `ANDROID_KEY_PASSWORD`

Do not commit the keystore or passwords to Git. Keep a secure backup of the keystore. When all four secrets are configured, the same workflow also builds and uploads the `nitro-rush-play-store-aab` artifact.

## Important

- The app ID is `com.mdsorbit.nitrorush`.
- The display name is **Nitro Rush**.
- This is a branded adaptation of OpenRally. The original MIT license and upstream attribution must remain included.
- A successful build does not guarantee Google Play approval. Test gameplay, privacy/data disclosures, age/content rating, store listing assets, target API requirements, and Play Console testing requirements before release.
