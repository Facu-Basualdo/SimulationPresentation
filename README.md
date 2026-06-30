# Simulación de Capacidad Máxima — miFACU

Presentación web de una sola página para la defensa académica del trabajo de
**Simulación 2026 — UTN FRRE**. Modela, mediante simulación de eventos discretos
(DES), el punto de saturación del servidor de **miFACU** (plataforma de gestión
académica) bajo distintas cargas de usuarios concurrentes.

**Grupo:** Los Pseudoaleatorios — Basualdo Alvarez Facundo · Dorrego Romina Evelyn ·
Drose Juan Ignacio · Neira Nicolas.

## Contenido

La presentación tiene 6 slides:

1. **Portada** — título, materia e integrantes.
2. **Escenario** — qué es miFACU y el problema de saturación.
3. **Objetivo** — determinar el punto de saturación (modelo DES, pool de 50 conexiones, timeout de 3 s).
4. **Variables** — tiempo entre llegadas y tiempos de respuesta por endpoint (μ, σ).
5. **Resultados** — capacidad máxima (λ ≈ 107,7 req/s), zonas de operación y escenarios de carga.
6. **Conclusión** — cuello de botella y recomendaciones.

## Características

- **Single-file:** todo el HTML, CSS, JS y el logo (en base64) están inline en
  `index.html`. No depende de archivos externos.
- **Navegación:** flechas `←` `→`, barra espaciadora (`Shift`+espacio retrocede),
  `Home`/`End`, botones, dots e indicador de progreso. Soporta swipe táctil.
- **Diseño:** paleta basada en el logo de miFACU (azul royal), fuente Geist,
  responsive para notebook y proyector.

## Uso local

Abrí `index.html` directamente en el navegador, o serví la carpeta:

```bash
npx serve .
```

## Estructura

```
.
├── index.html         # La presentación (single-file, logo embebido en base64)
├── assets/
│   └── logo.jpeg      # Logo de miFACU (fuente; el HTML no depende de él)
├── vercel.json        # Configuración de sitio estático
└── README.md
```

> Nota: la carpeta de assets se llama `assets/` (no `public/`) a propósito.
> Vercel toma automáticamente una carpeta `public/` como output directory cuando
> no hay build, lo que ocultaría el `index.html` de la raíz.

## Despliegue

Sitio estático desplegado en **Vercel**. Cada `git push` a `main` redeploya
automáticamente. Para importarlo: [vercel.com/new](https://vercel.com/new) →
Import del repo → Framework **Other**, sin build command → Deploy.
