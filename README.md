# Releases

Public downloads for projects whose source repositories may be private.

| App | Description | Download |
| --- | --- | --- |
| OverSight | Monitors a Mac's mic, webcam, screen capture, keyboard event taps, and remote access sessions, naming the app responsible. | [macOS](https://github.com/samueljason0508/releases/releases/tag/oversight-latest) |
| Keluli | AI meeting assistant with live transcription, media-file transcription, multi-language recognition, screen-aware answers, and a local `omp` model gateway. | [macOS and Windows](https://github.com/samueljason0508/releases/releases/tag/keluli-build-7) |

Each app keeps exactly one release here, with an app-scoped tag, so products can
share this repository without tag collisions and without old builds piling up.

OverSight is ad-hoc signed: right-click the app and choose Open on first launch.
It auto-updates from [`products.json`](products.json) in this repository, which
always describes the asset currently attached to `oversight-latest`.
