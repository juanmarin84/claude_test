# White House Miami — Recorrido 3D web

Versión web (Three.js) del proyecto de Unreal Engine **WhiteHouse** con sus dos niveles:

- **Inicio**: pantalla de entrada con el logo y el botón *Inicio*.
- **Whitehouse**: maqueta 3D navegable (girar, acercar, desplazar), menú *Pisos* (Piso 1, 2, 3 y Vista general en planta) y *Recorrido 360* (Panoraven).
  En Piso 1 aparecen los botones **2D / 3D** con los planos P1 y P1_3D_U alineados sobre el modelo; siempre abre primero el 3D.

Archivos: `index.html` (visor), `assets/whitehouse.glb` (modelo exportado desde Unreal con el exportador glTF, sin la carpeta Entorno ni Agua_Bahia), `assets/P1.webp`, `assets/P1_3D_U.webp`, `assets/logo.png`, `assets/grupos.json` (pisos de cada objeto) y `lib/` (Three.js r160).

## Ambiente realista (noviembre 2026)

- **Cielo**: degradado atmosférico HDR con halo y disco solar; sol de tarde (elevación 38°, azimut 196°) con sombras suaves 4K.
- **Nubes**: capa volumétrica procedimental animada (raymarch sobre una capa de 1,4–2,1 km), sin texturas.
- **Mar**: `Water.js` con reflejos, olas animadas, sombras y color turquesa cerca de la isla que se vuelve azul profundo mar adentro.
- **Materiales**: texturas procedimentales propias en `assets/tex/` (pasto, grava, concreto, adoquín, travertino, deck) proyectadas en coordenadas de mundo con variación macro para que no se note la repetición; estuco blanco sutil, vidrio y metales PBR, agua de piscina animada con cáusticas en el fondo.
- **Postprocesado**: oclusión ambiental GTAO, brillo suave (bloom) y tonos ACES.
- **Calidad**: en celulares se apagan GTAO y MSAA automáticamente. Se puede forzar con `?calidad=alta` o `?calidad=media`.
