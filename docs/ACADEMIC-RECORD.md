# Academic Record — Wave Field 3D Engine

**UUON Foundation Inc. — Phillip Aguilar Ruiz III**

---

## Origin

| Field | Value |
|-------|-------|
| Author | Phillip Aguilar Ruiz III |
| Organization | UUON Foundation Inc. |
| Engine Name | Wave Field 3D Engine |
| Repository | uuon-wave-field-3d-engine |
| Version | 1.0.0 |
| License | USAL-1.0 |

---

## Original Contribution Scope

1. **`WFE_surfCoord(shape, x, y, z)`** — the unified surface coordinate abstraction mapping sphere (atan2+acos), cube (L1 norm), and pyramid (radial+axial) into a single scalar `s` shared across all 24 algorithms. Enables the catalog to be shape-agnostic without branching inside any algorithm.

2. **The `fn(x,y,z,t,p,s)` catalog interface** — 24 wave classes normalized through one function signature with shared parameterization `{A,k,w,oct}`. The individual equations are prior art. The registry design applying them uniformly through a single callable surface deformation abstraction is original.

3. **`WFE_bake()` — deterministic frame sampler** — direct path from any catalog entry to a time-sampled Float32Array sequence, reproducible from P alone.

4. **`WFE_buildGLB()` — morph-target GLB encoder** — hand-built GLTF 2.0 implementation that correctly encodes delta-position morph targets and weight-track animations without the GLTFExporter dependency. Built specifically to fix the r128 15-byte silent failure on morph-target exports.

5. **Public/proprietary architecture split** — the design separating the renderer shell (index.html, public) from the engine core (core/engine.js, licensed) via the `window.WFE` API surface.

---

## Mathematical Prior Art (Not Claimed)

Individual wave equations are prior art. The math is not claimed as invention. Only the architecture is IP.

---

## Known Limitations at v1.0.0

- N-class algorithms use sin-hash, not gradient Perlin
- Normal-direction displacement breaks on non-convex geometry
- No graph serializer
- No API server
- No persistence layer

---

## Extension Record

| Version | Extension |
|---------|-----------|
| 1.0.0 | Initial release — 24 algorithms, morph-target bake, GLB/OBJ export, public/proprietary split |
| — | Graph serializer (next) |
| — | Node.js API server / headless render |
| — | True gradient Perlin noise |

---

*Provenance record — not a patent application.*
