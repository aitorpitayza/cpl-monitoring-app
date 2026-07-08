# ✈️ Ruta fATPL — Horas para la CPL(A) EASA

Aplicación web (PWA) para llevar el control de **horas de vuelo y requisitos de emisión de la CPL(A)** bajo EASA Part-FCL, pensada para la **ruta modular hacia el ATPL frozen**. Funciona en el iPhone como una app más: icono propio, pantalla completa y sin conexión.

Sin cuentas, sin servidores y sin dependencias: un único `index.html` con todo dentro. Tus horas se guardan en el propio dispositivo (`localStorage`).

## Qué controla

**Requisitos de emisión de la CPL(A)** (Part-FCL, Apéndice 3 E — curso modular), calculados en tiempo real:

| Requisito | Mínimo |
|---|---|
| Horas totales de vuelo | 200 h |
| Como piloto al mando (PIC) | 100 h |
| Travesía (cross-country) como PIC | 20 h |
| Vuelo nocturno | 5 h |
| Instrucción instrumental | 10 h (acreditada si tienes IR) |
| Doble mando del curso CPL | 25 h (15 h con IR) |
| En avión complejo | 5 h |

**Cursos de la ruta modular**, cada uno con sus mínimos, sus casillas y sus prerrequisitos:

1. **Habilitación de vuelo nocturno (VFR N)** — FCL.810
2. **IR(A) SEP** — Apéndice 6 (50 h de instrucción; avión/simulador por separado)
3. **Habilitación de clase MEP** — FCL.720.A
4. **Extensión IR a multimotor (puente MEP-IR)** — Apéndice 6 A.14
5. **Curso CPL(A) modular** — Apéndice 3 E
6. **UPRT avanzado** — FCL.745.A

Las horas de avión de cada curso **suman automáticamente** a los contadores de la CPL (las de simulador no cuentan como tiempo de vuelo). Los **exámenes (skill test)** tienen su propio campo y se apuntan como PIC. Al marcar la IR como completada, el curso CPL pasa de 25 h a 15 h y la instrucción instrumental aparece como acreditada.

También incluye los hitos generales: travesía VFR de 300 NM, los 14 teóricos ATPL y el médico de Clase 1.

## Cómo publicarla (GitHub Pages)

1. Crea un repositorio y sube todos los archivos de este proyecto.
2. En el repositorio: **Settings → Pages → Branch: `main` / carpeta `/ (root)` → Save**.
3. En un par de minutos tendrás la app en `https://TU_USUARIO.github.io/TU_REPO/`.

## Cómo instalarla en el iPhone

1. Abre la URL anterior en **Safari**.
2. Toca **Compartir** (el cuadrado con la flecha) → **Añadir a pantalla de inicio**.
3. Listo: se abre a pantalla completa, con su icono, y **funciona sin conexión** gracias al service worker.

> Los datos se guardan en el dispositivo. Si borras el historial/datos de sitios web de Safari, se pierden; el botón «Borrar todos los datos» de la app solo borra los de la propia app.

## Estructura del proyecto

```
├── index.html            # La app completa (HTML + CSS + JS)
├── manifest.webmanifest  # Metadatos de instalación (nombre, icono, colores)
├── sw.js                 # Service worker: modo sin conexión
├── icon-180.png          # Icono para iOS (apple-touch-icon)
└── icon-512.png          # Icono para el manifest / Android
```

## Aviso importante

Los objetivos reflejan los **mínimos reglamentarios** del Part-FCL (Reglamento (UE) n.º 1178/2011 y enmiendas) y el orden de los cursos es orientativo. Esta app es una ayuda de planificación personal, **no un documento oficial ni un logbook**: confirma siempre créditos, prerrequisitos y requisitos exactos con tu ATO y con tu autoridad (AESA en España), ya que tu caso puede tener particularidades.

## Licencia

MIT — úsala, modifícala y compártela libremente.
