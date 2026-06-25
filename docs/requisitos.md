# Etapa 1 — Relevamiento de requisitos

**Escenario asignado:** Tema 2 - Estudio Multimedia
**Programas que tuvimos que analizar:** Audacity, Blender, Inkscape, GIMP, Krita y OBS Studio

## Cómo trabajamos esto

Lo primero que hicimos fue meternos a la web oficial de cada programa para sacar los requisitos recomendados (no los mínimos, que es lo que pedía la consigna). En algunos casos como Blender y OBS la info estaba clara, pero con Inkscape y Audacity tuvimos que buscar un poco más en foros y wikis porque las páginas oficiales no dan muchos detalles de hardware.

La idea que usamos para armar la PC fue: agarrar el requisito más alto entre todos los programas, en cada categoría (CPU, RAM, GPU, etc.) y armar una compu que cumpla o pase ese techo. Así nos asegurarse de que la máquina banque cualquiera de los 6 programas, incluso usando varios al mismo tiempo (por ej. renderizando en Blender mientras se edita en Krita y de fondo grabás con OBS, que es una situación bastante típica en un estudio multimedia real).

De los 6, el que pide más potencia con diferencia es **Blender** (por el render 3D, las simulaciones y el compositing). Después viene **OBS Studio** por el tema de codificar video en vivo. Los otros cuatro (Krita, GIMP, Inkscape, Audacity) son livianos en comparación, pero cada uno aporta su requisito particular: Krita/GIMP/Inkscape necesitan buena fidelidad de color, y Audacity necesita baja latencia de audio más que potencia bruta.

## Tabla comparativa

| Software | SO compatible | CPU recomendada | RAM recom. | Almacenamiento | GPU |
|---|---|---|---|---|---|
| Blender | Windows 10/11, macOS, Linux | 8+ núcleos | 32 GB (64 en escenas pesadas) | SSD NVMe para SO/apps + 1-2 TB para proyectos | NVIDIA RTX, 8 GB+ VRAM (CUDA/OptiX) |
| OBS Studio | Windows 10/11, macOS 12+, Linux | 6-8 núcleos (o se descarga en NVENC) | 16 GB | SSD dedicado para grabar | NVIDIA GTX 1660+ / RTX (NVENC) |
| Krita | Windows 10/11, macOS, Linux | Quad-core 4 GHz+ | 16 GB | SSD, 512 GB+ | GPU moderna (Vulkan/Direct3D 11/OpenGL 3.0), mejor si es NVIDIA |
| GIMP | Windows 10/11, macOS, Linux | Multinúcleo 2.5 GHz+ | 8-16 GB | SSD, ~2 GB de instalación | OpenGL 3.3, 512 MB+ VRAM (OpenCL) |
| Inkscape | Windows 10/11, macOS, Linux | Quad-core 2.5 GHz+ (pesa más el single-core) | 8 GB | SSD, ~1 GB | OpenGL 2.0+, ayuda tener 1 GB+ VRAM |
| Audacity | Windows 10/11, macOS, Linux | Dual-core 2 GHz+ | 4 GB | SSD, depende del proyecto | No usa GPU |

### Lo que termina pidiendo el conjunto (lo que define la PC)

| Recurso | Valor que nos tiene que dar la propuesta | ¿Por qué programa? |
|---|---|---|
| CPU | 8+ núcleos, multinúcleo potente | Blender |
| RAM | 32 GB | Blender |
| GPU | NVIDIA RTX con 8 GB+ de VRAM | Blender (OptiX) + OBS (NVENC) |
| Almacenamiento | SSD NVMe + disco grande para proyectos | Blender / OBS |
| Monitor / color | Buena cobertura sRGB, ΔE bajo | Krita / GIMP / Inkscape |

## Algunas notas que sacamos de cada programa

- **Blender:** entre más núcleos tenga la CPU mejor (render por CPU, física, fluidos, compositing), y una GPU NVIDIA RTX ayuda muchísimo porque acelera el render en Cycles con OptiX. La VRAM es importante porque ahí entran las escenas y texturas pesadas. Recomiendan 32 GB de RAM y un SSD rápido más algo de almacenamiento grande para los proyectos.
- **OBS Studio:** depende bastante de a qué resolución/FPS se grabe y qué encoder se use. Si usás NVENC (que tienen las GeForce GTX serie 16 en adelante y las RTX) la codificación se la banca la GPU y no la CPU, entonces podés grabar/transmitir sin que se note tanto en el resto del trabajo.
- **Krita:** pide 16 GB de RAM y una GPU que no sea muy vieja, porque el lienzo se acelera por GPU. Además recomiendan usar tableta gráfica para pintar, cosa que con mouse se hace bastante incómodo.
- **GIMP:** anda mejor con 8-16 GB de RAM, tiene soporte OpenCL para algunos filtros y un SSD ayuda con los tiempos de carga.
- **Inkscape:** acá lo que más importa es el rendimiento de un solo núcleo (no tanto la cantidad), porque carga todo el SVG en memoria. Con 8 GB de RAM va cómodo.
- **Audacity:** es el más liviano de todos, con 4 GB de RAM y un CPU de 2 GHz ya anda bien. Lo que más importa en este caso es tener una buena entrada de audio (micrófono o interfaz), no tanto el hardware de cómputo.

## Sistema operativo elegido: Windows 11 Pro 64-bit

Los 6 programas corren en Windows, macOS y Linux, así que la decisión no fue por compatibilidad sino por cuál plataforma le saca mejor jugo al hardware que elegimos:

- Los drivers de NVIDIA para CUDA/OptiX (que usa Blender) y NVENC (que usa OBS) están más maduros y son más fáciles de instalar/actualizar en Windows. Además existen los drivers "NVIDIA Studio" que están pensados justo para este tipo de uso (creación de contenido).
- En Windows es más fácil que funcione cualquier periférico: tabletas Wacom, placas de captura, interfaces de audio, micrófonos USB, etc.
- En general hay más soporte y comunidad para estos 6 programas en Windows.

## Fuentes que consultamos

- Blender Foundation - sección de Requirements en blender.org/download y el manual de Blender para la parte de GPU Rendering.
- OBS Project - System Requirements de la documentación oficial.
- Krita - página de descarga oficial (krita.org).
- GIMP - documentación oficial (docs.gimp.org).
- Inkscape - foros y guías del proyecto.
- Audacity - System Requirements del manual/wiki oficial.

(Los links puntuales que usamos están en el repositorio, en la sección de justificación.)