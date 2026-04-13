# syntax=docker/dockerfile:1
#
# Patched Music Assistant: Official image + YouTube Music no-premium patches
#
# =============================================================================
# HOW TO UPDATE WHEN MERGING UPSTREAM
# =============================================================================
# 1. Bump BASE_VERSION default below to match build.yaml
# 2. Verify the sed patterns still match the upstream ytmusic provider code:
#    https://github.com/music-assistant/server/blob/main/music_assistant/providers/ytmusic/__init__.py
# 3. If upstream changed the target strings, update the sed commands accordingly
# 4. The "Verify patches applied" check will fail the build if Patch 1 no longer matches
# =============================================================================
ARG BASE_VERSION=2.8.4
FROM ghcr.io/music-assistant/server:${BASE_VERSION}

# Apply YouTube Music patches
RUN YTMUSIC_INIT="/app/venv/lib/python3.13/site-packages/music_assistant/providers/ytmusic/__init__.py" && \
    # Patch 1: Bypass Premium check
    sed -i 's/return stream_format\["format_id"\] == "141"/return True  # Patched: skip premium check/' "$YTMUSIC_INIT" && \
    # Patch 2: Widen format selector
    sed -i 's/"m4a\/bestaudio"/"bestaudio\/best"/' "$YTMUSIC_INIT" && \
    # Patch 3: Add fallback player clients
    sed -i 's/"player_client": \["web_music"\]/"player_client": ["web_music", "mweb", "android_music"]/' "$YTMUSIC_INIT" && \
    # Verify patches applied
    grep -q 'skip premium check' "$YTMUSIC_INIT" && echo "Patches applied successfully" || exit 1
