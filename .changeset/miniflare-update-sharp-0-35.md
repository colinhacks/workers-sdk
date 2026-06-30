---
"miniflare": patch
---

Update `sharp` to 0.35.2

`sharp` 0.35 removes its `install` lifecycle script, so package managers that block dependency build scripts by default (such as pnpm 11+) no longer require an explicit build approval for it when installing `miniflare`/`wrangler`. The local Images binding keeps using the same prebuilt `sharp` binaries, so image transforms in local dev are unaffected.

This release also reworked `sharp`'s `FormatEnum` types: libvips reports AVIF inputs under the `heif` container, so the Images binding `/info` endpoint now correctly returns `image/avif` for AVIF images instead of treating them as an unsupported type.
