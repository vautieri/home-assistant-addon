# Home Assistant Addon Repository (Patched)

Custom HA addon repository with patched versions of addons.

This is the Home Assistant App repository for Music Assistant for a convenient way to run the [Music Assistant Server](https://github.com/music-assistant/server)

### Music Assistant (Patched)
Official Music Assistant with YouTube Music no-premium patches baked in.

**Patches:**
1. Bypass Premium check
2. Widen format selector (bestaudio/best)
3. Add fallback player clients (mweb, android_music)

## Installation

1. In Home Assistant, go to **Settings → Add-ons → Add-on Store**
2. Click the three dots (top right) → **Repositories**
3. Add: `https://github.com/vautieri/home-assistant-addon`
4. Install **Music Assistant (Patched)**

## Updating

When a new MA version releases:
1. Update `BASE_VERSION` in `music_assistant_patched/Dockerfile` and `build.yaml`
2. Update `version` in `config.yaml`
3. Push to main → GitHub Action builds the new image
4. Update the addon in HA

[repository-badge]: https://img.shields.io/badge/Add%20repository%20to%20my-Home%20Assistant-41BDF5?logo=home-assistant&style=for-the-badge
[repository-url]: https://my.home-assistant.io/redirect/supervisor_add_addon_repository/?repository_url=https%3A%2F%2Fgithub.com%2Fmusic-assistant%2Fhome-assistant-addon
