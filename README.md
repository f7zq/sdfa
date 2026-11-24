# ATLAS (Android)

Download manager and media player. Kotlin + Jetpack Compose, black & gold liquid-glass UI.
Full technical plan: [`docs/ATLAS_PLAN.md`](docs/ATLAS_PLAN.md).

## Status

**Phase 1 — app foundation** (code written, not yet built or run on a device):
theme, splash, Home, bottom navigation, Settings (language AR/EN with RTL, dark/light), About,
and the `ads/` package prepared with a no-op `AdsManager`. No ads run in this phase.

## Build and run

1. Open the `ATLAS` folder in a current Android Studio (it creates `local.properties` with the SDK path).
2. **Update versions first**: `gradle/libs.versions.toml` and `compileSdk`/`targetSdk` in `app/build.gradle.kts`
   are conservative baselines that could not be checked against the latest releases.
3. Set `atlas.applicationId` in `gradle.properties` to the package name registered for ATLAS in AdMob.
4. Run the `debug` variant. Debug uses Google test ad IDs and the `.debug` package suffix.

## Phase 1 test checklist

- Cold start shows the system splash, then the animated ATLAS splash, then Home.
- Bottom bar switches Home / Downloads / Library / More and keeps its state.
- More → Settings → pick العربية: the whole UI flips to RTL; pick English: back to LTR; pick System default.
- Settings → Dark mode off: light variant; kill and reopen the app: the choice is kept.
- Items marked "Coming soon" are not clickable and do not pretend to work.
- Rotate the device and use large font sizes: no clipped text.

## Not in Phase 1

Share Intent, downloads, queue, playlists, library, player, subtitles, browser, private folder, ads.
