# Almacen Releases

Releases oficiales de [Almacén](https://github.com/PapiScholz/Almacen) — POS + WMS para PyMEs.

Descargá el instalador desde la sección **Releases** de este repositorio.

## Repos relacionados

Almacén vive en cuatro repos que van **siempre juntos**: un cambio en uno suele pedir un cambio en otro. Antes de
tocar un contrato (rutas del Worker, formato de releases, `worker-api.mjs`), revisá los otros tres.

| Repo | Local | GitHub | Qué es |
|---|---|---|---|
| Almacen | `../Almacen` | [PapiScholz/Almacen](https://github.com/PapiScholz/Almacen) | La app (Electron + Next): POS, licencia, actualizador y workflow de release |
| Almacen-releases | `../Almacen-releases` | [PapiScholz/Almacen-releases](https://github.com/PapiScholz/Almacen-releases) | Instaladores publicados. **En retiro**: pasan a un R2 privado que sólo entrega el Worker |
| almacen-license-worker | `../almacen-license-worker` | [NANDI-Services/almacen-license-worker](https://github.com/NANDI-Services/almacen-license-worker) | Cloudflare Worker: licencias, nube, cobro por Mercado Pago, descarga y actualizaciones |
| almacen-landing | `../almacen-landing` | [NANDI-Services/almacen-landing](https://github.com/NANDI-Services/almacen-landing) | Sitio comercial (Astro en Cloudflare Pages): demo, precios, compra, baja y arrepentimiento |

Contratos que los atan:
- **landing ↔ Worker:** `almacen-landing/src/lib/worker-api.mjs` (`/pricing`, `/checkout`, `/download`, `/requests`).
- **app ↔ Worker:** validación de licencia, sync, copias y, desde la migración a R2, `/updates/…` del actualizador.
- **release de la app → instaladores:** hoy el workflow de `Almacen` publica en `Almacen-releases`; el plan de
  migración a R2 privado está en `Almacen/docs/specs/2026-11-02-releases-r2-privado/plan.md`.
