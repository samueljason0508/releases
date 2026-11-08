# Agent guide for this repository

This repository holds **public downloads only**. No application source lives
here; each app is built from its own (often private) source repository and
publishes here.

## Rules

- Keep **exactly one release per app**. Replace its asset in place
  (`gh release upload <tag> <file> --clobber`) and delete any superseded
  release together with its tag. Never accumulate old builds.
- Current tags: `oversight-latest` (OverSight, `OverSight.zip`) and the current
  Keluli build tag (`Keluli-<version>-arm64.dmg`). Tags are app-scoped so apps
  never collide.
- Never touch another app's release, assets, notes, or the repository's Latest
  marker when publishing an app.
- Upload end-user binaries in native installable formats only. Never upload
  source archives; GitHub's automatic "Source code" links are not assets and
  cannot be removed.
- Keep `README.md` in sync: one table row per app, linking to that app's single
  release tag.

## products.json

`products.json` is OverSight's live update feed. The app fetches it from
`raw.githubusercontent.com` on the `main` branch, so `main` must stay the
default branch.

Its `OverSight.version`, `zip`, and `sha256` must always describe the asset
currently attached to `oversight-latest`. OverSight verifies the download's
SHA-256, bundle identity, version, and code signature, and rejects any `zip`
URL other than the fixed `oversight-latest` path - so publish the asset first,
then update the feed. A mismatch silently blocks every user's update.

OverSight's release workflow lives in the private `oversight-extensions`
repository and writes both the release and this feed using a fine-grained token
scoped to this repository.
