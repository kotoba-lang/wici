# kotoba-lang/wici

Software half of [wici.ai](https://wici.ai/): a GPU that applications treat as
local while it lives elsewhere.

| WiCi | here |
|---|---|
| WiCi Protocol — remote GPU appears local | `wici.device/IDevice` + `wici.remote/remote` (same protocol, proxied) |
| Wire between device and GPU | `wici.protocol` — EDN request/response, transport-agnostic (`kotoba.wire`, `drpc`, WebSocket, loopback) |
| Models larger than local VRAM | `wici.place/place` — local → remote → none |
| Custom wireless chip, ~1.5 ms radio | **not here** — hardware |

`wici.device/local` is a CPU reference backend; a real GPU backend (`kotoba-lang/gpu`,
`webgpu`) implements `IDevice` and nothing above changes.

Test: `kbb -M:test`
