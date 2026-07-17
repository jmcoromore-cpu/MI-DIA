# Mi Día · Focus

Organizador personal en **un solo archivo HTML**, sin dependencias, sin servidor y sin build. Funciona offline, se instala como app en el iPhone y guarda todo en el propio dispositivo. Reúne cuatro herramientas en una: agenda diaria/semanal, lista de pendientes, seguimiento de hábitos por áreas de vida y resumen mensual, con sincronización de los calendarios de iCloud.

![HTML](https://img.shields.io/badge/HTML-vanilla-e34f26) ![Sin dependencias](https://img.shields.io/badge/dependencias-0-0d9488) ![PWA](https://img.shields.io/badge/PWA-instalable-2dd4bf) ![Licencia](https://img.shields.io/badge/licencia-MIT-informational)

## Qué hace

La app tiene cuatro secciones, accesibles desde la barra inferior:

###  Organización
Agenda del día en formato de tira horaria (timeline), con los eventos colocados por hora y solapamientos repartidos en carriles automáticamente. Una línea roja marca la hora actual. Cambia a **vista semana** para ver los siete días de un vistazo y planificar el domingo. Los eventos se marcan como hechos con un toque y muestran una barra de progreso del día.

**Entrada rápida en lenguaje natural:** escribe (o dicta) frases como:

- `mañana de 9 a 10 estudiar`
- `el lunes a las 5 de la tarde gimnasio`
- `pasado mañana reunión` *(sin hora)*
- `el 25 a las 8 y media cena`

La app interpreta fecha, hora y título, y abre la actividad ya rellenada para que la revises y guardes. El **micrófono** (Web Speech API) permite dictar la actividad en Safari.

###  Hacer
Lista de pendientes sin fecha. Al marcar uno, se tacha y desaparece con animación. Con el botón 📅 conviertes un pendiente en una actividad planificada en el día que elijas.

###  Día a día
Un **heptágono/radar** con siete áreas de la vida  que valoras de **1 a 5** cada día. La forma del radar se expande según tus notas. Cuando valoras las 7 áreas, se enciende una **racha** de días completos.

### Resumen
Vista mensual con una rejilla tipo calendario por cada área: la intensidad del color refleja la nota (1–5), se ve la racha por hábito y el total de puntos del mes. Puedes tocar cualquier día para corregir su valoración.

## Calendarios de iCloud

Puedes vincular los calendarios públicos de tu iPhone para verlos junto a tus actividades, cada uno con su color original.

1. En el iPhone: **Calendario → Calendarios → ⓘ** junto a un calendario → **Calendario público** → **Compartir enlace**.
2. En la app: **Ajustes (⚙️) → Calendarios de iCloud** → pega el enlace (`webcal://…` o `https://…`) → **Añadir**.
3. Repite con cada calendario (cada color de tu iPhone es un calendario distinto).

La sincronización descarga y analiza los `.ics`, expande los eventos recurrentes (reglas `RRULE` diarias, semanales, mensuales y anuales, con `EXDATE` y eventos cancelados), y respeta el color y el nombre de cada calendario. También puedes **importar un archivo `.ics`** a mano.

> Nota: al ser una app 100% de navegador sin servidor propio, la descarga del `.ics` se intenta de forma directa y, si el navegador la bloquea por CORS, a través de proxies públicos de reenvío.

## Privacidad y datos

Todos tus datos —actividades, pendientes y valoraciones— se guardan **solo en este dispositivo**, en el almacenamiento local del navegador. No hay cuentas, no hay nube propia, no se envía nada a ningún servidor.

Desde **Ajustes** puedes **exportar una copia de seguridad** en JSON y **restaurarla** cuando quieras. Conviene exportar de vez en cuando, porque si borras los datos del navegador se pierde la información.

## Puesta en marcha

Al ser un único archivo, no hay instalación ni dependencias.

**Uso local:** abre `index.html` en cualquier navegador (doble clic).

**Instalar como app en el iPhone (recomendado):**
1. Sube el archivo a un hosting con HTTPS. Lo más fácil: **GitHub Pages** (Settings → Pages → Deploy from branch → `main` / root). Renombra el archivo a `index.html`.
2. Abre la URL en **Safari**.
3. **Compartir → Añadir a pantalla de inicio**. Se instala a pantalla completa, con su icono y colores propios (tema claro/oscuro automático).

## Tecnología

- **HTML + CSS + JavaScript vanilla**, sin frameworks ni librerías externas.
- **PWA** con metadatos para instalación en iOS y pantalla completa.
- **localStorage** para persistencia, con migraciones de esquema entre versiones.
- **Web Speech API** para el dictado por voz.
- **Parser propio de iCalendar (.ics)** con expansión de eventos recurrentes.
- Diseño *responsive* pensado para móvil, con tema claro y oscuro automático.

## Estructura del repositorio

```
MI-DIA/
└── index.html   # toda la app: estructura, estilos y lógica en un único archivo
```

## Licencia

MIT. Si te resulta útil, adáptalo y compártelo.
