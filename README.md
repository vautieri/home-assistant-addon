# Home Assistant Addon Repository (Patched)

Custom HA addon repository with patched versions of addons.

## Addons

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
