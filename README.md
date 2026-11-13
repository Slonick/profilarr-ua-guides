# profilarr-ua-guides

Profilarr database for Radarr and Sonarr setups that pull from Ukrainian trackers.

Only releases with a Ukrainian audio track are accepted. A release is rejected when Radarr or Sonarr can't detect Ukrainian and the title has no Ukrainian audio tag either (`Ukr`, `2xUkr`, `2Ukr`, `UKR_ENG`, `Укр`). Subtitle-only tags such as `Sub Ukr` or `UKRsub` don't count. Radarr and Sonarr read `Ukr` after `sub` as an audio language too, so a title that lists Ukrainian subtitles without a Ukrainian audio tag (`Eng | sub Ukr/Eng`) is rejected as well.

Nothing gets a bonus. Release groups, streaming-service tags and repack tags only reflect how a release is named on Ukrainian trackers, not how good it is, and bonuses for them would make the apps re-download files just to get a differently named copy. Quality and size decide; custom formats only filter. A file without Ukrainian audio is replaced as soon as a Ukrainian release shows up.

## Usage

In Profilarr, go to Databases, click +, and link:

```
https://github.com/Slonick/profilarr-ua-guides
```

## Profiles

### Slonick - Movies

For Radarr. 2160p Remux comes first, followed by Bluray and WEB in 2160p and 1080p. Lower qualities down to SD stay enabled for titles where nothing better exists.

Filters out 3D, BR-DISK, upscales, extras and sing-along versions.

### Slonick - Series

For Sonarr. 2160p Remux and WEB come first, followed by 1080p and 720p. DVD and SD are allowed too, since plenty of older shows were never released in anything better.

Filters out BR-DISK, upscales and extras.

## Media management

Ukrainian trackers behave differently from the international scene, and the settings follow that:

- **No size limits.** Releases are scarce and often carry several Ukrainian dubs plus the original audio, which pushes the size up. A cap would only throw away the one release that exists. Within the same quality and score, the larger release wins.
- **Torrent only, 60 minute delay.** There is no Usenet here, and different qualities of the same title usually appear days apart rather than minutes, so a long delay only postpones the grab. The top quality is grabbed immediately.
- **Propers and repacks are not preferred.** Uploaders update the existing torrent instead of posting a PROPER or REPACK, so the tags almost never appear.
- **Audio languages in file names.** New files get the audio tracks in their names, for example `[UK+EN]`, so it's easy to see which files have a Ukrainian track. Folder names are unchanged.

Profilarr needs these selected before it will sync the quality profiles.
