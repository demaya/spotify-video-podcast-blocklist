# Spotify Video Podcast Blocklist

Block Spotify video podcasts by blocking known Spotify video delivery domains.

This repository provides a simple domain blocklist for users who want to disable the **video podcast feature in Spotify** while continuing to use Spotify for audio playback.

It is especially useful for network-level blockers such as **Pi-hole**, **AdGuard Home**, **NextDNS**, or router/firewall DNS blocklists.

## Why this exists
Many users want to remove video podcast behavior in the Spotify app to reduce distractions, save bandwidth, and keep a cleaner audio-only experience.

Community context and discussion:
- Reddit thread: https://www.reddit.com/r/pihole/comments/1gjtq93/looking_to_block_video_podcasts_in_spotify_block/

## Blocklist URL
Use this raw URL in your DNS/blocking tool:

`https://raw.githubusercontent.com/demaya/spotify-video-podcast-blocklist/refs/heads/main/spotify-video-podcast-blocklist.txt`

## Usage
1. Add the blocklist URL to your blocklist provider (for example, Pi-hole adlists).
2. Update gravity / refresh blocklists.
3. Restart Spotify clients if needed.

## Repository contents
- `spotify-video-podcast-blocklist.txt`: domains used to deliver Spotify video podcast content.

## Notes
- Domains may change over time; updates are made as new endpoints are identified.
- If Spotify video still loads, refresh blocklists and verify DNS requests from your client.
