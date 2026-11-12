# White House Miami — Recorrido 3D web

Versión web (Three.js) del proyecto de Unreal Engine **WhiteHouse** con sus dos niveles:

- **Inicio**: pantalla de entrada con el logo y el botón *Inicio*.
- **Whitehouse**: maqueta 3D navegable (girar, acercar, desplazar), menú *Pisos* (Piso 1, 2, 3 y Vista general en planta) y *Recorrido 360* (Panoraven).
  En Piso 1 aparecen los botones **2D / 3D** con los planos P1 y P1_3D_U alineados sobre el modelo; siempre abre primero el 3D.

Archivos: `index.html` (visor), `assets/whitehouse.glb` (modelo exportado desde Unreal con el exportador glTF, sin la carpeta Entorno ni Agua_Bahia), `assets/P1.webp`, `assets/P1_3D_U.webp`, `assets/logo.png`, `assets/grupos.json` (pisos de cada objeto) y `lib/` (Three.js r160).
