# DealRadar — Samsung Android build

This is an early, **offline/demo Android app**, not a live coupon aggregator. It includes membership selections, category filters and locally saved favourites. The bundled `offers.json` is empty. It does not yet collect coupons, connect to Verizon/Netflix/AMC, verify entitlements, sync between two phones, or issue alerts. The refresh button reloads the bundled feed, not websites.

## Build an APK using only a Samsung phone

1. Download the **DealRadar-GitHub-Ready.zip** package from ChatGPT.
2. Open [github.com](https://github.com) in Samsung Internet and sign in or create a free account.
3. Create a **new repository** named `DealRadar` (choose **Private** if preferred). Do not initialise it with a README.
4. To upload this project from a phone, use the GitHub web interface **Add file → Upload files**. **GitHub's web upload does not unpack ZIPs**: extract the ZIP in Samsung My Files and upload its contents, preserving the directories, including the hidden `.github/workflows/build-apk.yml` file. Some mobile browsers make folder uploads awkward; if so, use a mobile Git client that supports pushing a folder, or use GitHub's web editor to create the workflow file at that path. You must keep the `app/` hierarchy intact.
5. Once uploaded, visit your repository's **Actions** tab. Choose **Build DealRadar APK**, then **Run workflow**. (A push to `main` also triggers the build.)
6. After the green success check, open that run, scroll to **Artifacts**, and download **DealRadar-Android-APK**.
7. Extract the downloaded artifact ZIP on your Samsung phone. Tap `app-debug.apk` and approve **Install unknown apps** for the app you're using to open it, if Android prompts you.
8. Open **DealRadar** from your home screen.

The debug APK is intended for personal testing, not Play Store distribution. Do not put passwords or subscription credentials into this prototype. APK installation from outside Play Store has risks; only install a build from your own trusted repository.

## For developers

Requires JDK 17, Android SDK 35, Gradle 8.9. Run `gradle assembleDebug`. Output: `app/build/outputs/apk/debug/app-debug.apk`.

Live coupons require legitimate authorised feeds/APIs or merchant partnerships, a backend updater, eligibility verification, and a shared-account service.
