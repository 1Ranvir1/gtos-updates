# GT OS updates

Public update feeds for GT OS, developed by Ranvir Singh.

## On the phone

One-time setup: install the signed GT OS updater bootstrap package supplied in
Releases over the existing GT OS Updater. Then open Settings → System → System
updates and check for updates. Future compatible ROM updates download on the
phone over HTTPS and use Android's signed A/B update engine.

The initial X6739 feed is intentionally empty: it establishes connectivity
without offering an older build or a test package as a real OS upgrade.
An actual install test requires a newer verified release, which will be listed
only after validation. No full OS update has yet been tested through this feed.

## Device support

Feeds live at `devices/<device>/<channel>.json`. Currently only Infinix GT 10 Pro
(X6739), Android 16 / GT OS based on Lineage 23.2 / UNOFFICIAL is being prepared.
Other phones require their own device-specific builds, signatures, partition
validation and hardware testing. An X6739 package is not a universal Android ROM.

## Release rules

- Publish only reviewed, cryptographically verified, compatible signed releases.
- Retain the original signing identity across updates.
- Never include private signing keys, tokens, user photos, backups or host logs.
- Upload packages as GitHub Release assets, then update the feed last.
- Feed entries include the exact SHA256, byte size, device/channel/version and
  actual build timestamp. Do not change timestamps to advertise an old build.
- A routine full A/B OTA must not request a wipe or downgrade.
- Keep bring-up/debug releases separate from production distributions.

The bootstrap updater APK is an app update only. It does not flash the phone,
change bootloader code or erase personal data. System images remain on the PC
until a compatible newer release is explicitly prepared and verified.
