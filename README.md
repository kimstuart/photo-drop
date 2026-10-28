# photo-drop

Serving-size photo copies for the EMA photo intake path. Created 28Oct26 (KimS+CC, EMA card ruling A9-R2 revised: GitHub route).

**What goes here:** JPEG copies already shrunk to a long edge of at most 1000 px and at most 256 KB, with all metadata stripped (no EXIF, no GPS, no colour profile). They are the files a site will serve, nothing more.

**What never goes here:** originals, anything with metadata, anything not meant to be public. The repo is public so that WordPress can fetch a file by its raw URL without a token.

**How it is used:** a Claude Code cloud session shrinks a photo, commits it under `YYYY/MM/<site>/<name>.jpg`, pushes, then asks the site's WordPress connector to sideload it from `https://raw.githubusercontent.com/kimstuart/photo-drop/main/<path>`. Once the attachment exists on the site, the copy here may be deleted; the site holds the serving file.

**Housekeeping:** start a fresh repo when this one passes a few hundred MB. Nothing in this repo is a backup of anything.
