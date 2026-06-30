---
"create-cloudflare": patch
---

Stop pre-approving `sharp`'s build script in generated projects

`miniflare` now depends on `sharp` 0.35, which no longer ships an `install` lifecycle script. Generated `pnpm-workspace.yaml` files therefore no longer pre-approve `sharp` under `allowBuilds`. `esbuild` and `workerd` are still pre-approved because they retain their install/`postinstall` scripts.
