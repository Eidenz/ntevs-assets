# ntevs-assets

Patch data for NTE Video Swap. The app downloads
it by itself; there is nothing to install from here by hand.

The Cinema Screen and Apartment TV swaps rely on patched copies of two game
blueprints. Game updates make those copies stale, so they are published here
instead of being built into the app. On launch the app reads `manifest.json`,
and if its `revision` is newer than what it has, it downloads that revision's
files, checks them against the checksums in the manifest, and re-applies your
Cinema and TV videos.

## Layout

- `manifest.json` describes the latest revision: the game version it was built
  for, the files of each slot with their size and SHA-256, and the byte offsets
  where the app writes the playlist length.
- `r<revision>/` holds the files of one revision. A published revision is never
  changed; a fix is a new revision.
