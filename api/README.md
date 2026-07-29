# Wave Field 3D Engine — API Layer (Planned)

The browser engine is complete. This documents the unbuilt server layer.

---

## Planned Stack

```
Node.js / Express
core/engine.js extracted as lib/algorithms.js (Node module)
PostgreSQL — P-vector state persistence
S3-compatible storage — GLB/OBJ artifact storage
```

---

## F=(P,E,R,C) Endpoints

### POST /api/v1/encode
Accept P vector → return deformed mesh JSON

### GET /api/v1/decode
Accept P as query params → stream static OBJ

### POST /api/v1/bake
Accept P + frame config → return animated GLB binary

### POST /api/v1/states
Save named P vector for reproducibility → return permalink

---

## Next Session Starting Point

Extract `WFE_ALG` and `WFE_surfCoord` from `core/engine.js` into `api/lib/algorithms.js` as a Node.js CommonJS module. The `fn(x,y,z,t,p,s)` interface is already testable without a renderer. That module is the foundation of the API server.

```javascript
// api/lib/algorithms.js target interface
const { WFE_ALG, WFE_surfCoord, WFE_bake } = require('./algorithms');
```
