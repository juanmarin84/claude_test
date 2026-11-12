# White House Miami — Recorrido 3D web

Versión web (Three.js) del proyecto de Unreal Engine **WhiteHouse** con sus dos niveles:

- **Inicio**: pantalla de entrada con el logo y el botón *Inicio*.
- **Whitehouse**: maqueta 3D navegable (girar, acercar, desplazar), menú *Pisos* (Piso 1, 2, 3 y Vista general en planta) y *Recorrido 360* (Panoraven).
  En Piso 1 aparecen los botones **2D / 3D** con los planos P1 y P1_3D_U alineados sobre el modelo; siempre abre primero el 3D.

Archivos: `index.html` (visor), `assets/whitehouse.glb` (modelo exportado desde Unreal con el exportador glTF, sin la carpeta Entorno ni Agua_Bahia), `assets/P1.webp`, `assets/P1_3D_U.webp`, `assets/logo.png`, `assets/grupos.json` (pisos de cada objeto) y `lib/` (Three.js r160).

## Ambiente realista (noviembre 2026)

- **Cielo y luz**: degradado atmosférico HDR con halo y disco solar; sol de tarde (elevación 38°, azimut 196°) intenso y luz de cielo alta para sombras suaves y azuladas.
- **Nubes**: capa volumétrica procedimental animada (raymarch sobre una capa de 1,4–2,1 km), sin texturas.
- **Mar poco profundo**: superficie transparente con olas a escala real (2,6 m y 6,5 m), reflejo del cielo y brillo del sol; se ve el fondo de arena con manchas de algas, cáusticas animadas y las sombras de la casa. El fondo baja de 3 m junto a la isla a unos 30 m mar adentro, y el color pasa de turquesa a azul profundo según la profundidad (absorción física por canal de color). Nivel del agua: −1,35 m. La isla tiene un muro de base bajo el agua.
- **Materiales**: texturas procedimentales propias en `assets/tex/` (pasto, grava, concreto, adoquín, travertino, deck) proyectadas en coordenadas de mundo con variación macro para que no se note la repetición; estuco blanco sutil, vidrio y metales PBR, agua de piscina y jacuzzi transparente con olas pequeñas y cáusticas animadas en el fondo y las paredes.
- **Palmas**: se mueven con el viento (tronco e inclinación por ráfagas, hojas ondeando hacia las puntas, sombras que también se mueven), con variación de color, puntas amarillentas y luz que atraviesa las hojas a contraluz.
- **Postprocesado**: oclusión ambiental GTAO, brillo suave (bloom) y tonos ACES.
- **Calidad**: en celulares se apagan GTAO y MSAA automáticamente. Se puede forzar con `?calidad=alta` o `?calidad=media`.
