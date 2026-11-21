# mtk-assets

MTK Download Agent binaries and Penumbra payloads for
[ALEJA Tool](https://github.com/lazaro-jesus/aleja-tool).

These files are **not** committed to the tool repo. `build.rs` in aleja-tool
downloads them once, on the first build, from this repo (raw.githubusercontent.com)
with SHA-256 verification, into `assets/mtk-da/` (gitignored) — the same pattern
as `assets/platform-tools/`. The tool then loads them from disk at runtime
(`load_from_file`); it never downloads them by itself.

## Layout

- `da/` — Download Agent binaries (MediaTek / OEM blobs, from Telegram channel
  GSM_RK, posts 12968–12971, downloaded 2026-11-21). Verified by header:
  `MTK_DOWNLOAD_AGENT` + file magic `0x99886622` at offset 0x64.
- `payloads/` — Penumbra extension payloads, built 2026-11-21 from
  [shomykohai/mtk-payloads](https://github.com/shomykohai/mtk-payloads)
  @ `c8e002c01e4a` with ARM GNU Toolchain 13.2.rel1. **License: AGPL-3.0.**

## Files (SHA-256)

| File | Size | SHA-256 |
|---|---|---|
| da/MTK_DA_V5.bin | 22483280 | aef234190ccb8145d2e3b8459741e9adb70f2caa8481aa216c1b25152afaca1f |
| da/MTK_DA_V6.bin | 9905212 | 96471e726fe2df28a2f16f73c1ed0dc0029aaa85e0fee55bfcd842712774c911 |
| da/oppo_2_MTK_AllInOne_DA.bin | 546508 | 4464c61ed2d2222a538a14a5eb09ca73ca36dbe6eeb6bfff28b924d6a72881f0 |
| da/xiaomi_9_DA_6765_6785_6768_6873_6885_6853.bin | 3866852 | 7404e6f1930b09f19a8afce94d7226dc9d13e392249fc68848ab56d3afd30ca9 |
| payloads/da_x.bin | 31500 | d0c8c9c736d94cc86cbfa50f584a6a05b0ef4126c053ea8fd4c8e980dcedc239 |
| payloads/da_xml.bin | 111916 | a33dff65aeba7434415284dd45c84ea283a60bbe6c874516bc035bf634ec3aa1 |
| payloads/extloader_v5.bin | 66 | c49ef064673887fe0cebd6a2980db9b5dea0161beb1e297662a0d50afbebe846 |
| payloads/extloader_v6.bin | 3832 | 8e9e7649f610461d8167feed2c3542d590698c73eac3eb5d5db67f7d57f28043 |
| payloads/brom_defuse.bin | 878 | bb71a9fd9ab62acf3ca5b51b620087d5f5bce675278f038bc877df25f102f47e |
| payloads/hakujoudai.bin | 29492 | b9f92f6f65f16fcd2a51d2d184c550a5593f7e1c3348297ae9c4e81cdda813d2 |
| payloads/sla_xml.bin | 232 | de003cf9125c9026c52d6c598d2ab007c48bca326f56a10c73ed5423fc5095df |
