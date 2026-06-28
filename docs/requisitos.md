# Etapa 1 — Relevamiento de requisitos

**Escenario asignado:** Tema 2 - Estudio Multimedia
**Programas que tuvimos que analizar:** Audacity, Blender, Inkscape, GIMP, Krita y OBS Studio

## Eleccion final de los PC

Arrancamos relevando los requisitos como pedía la consigna (ver la tabla más abajo, eso no cambió) pero después, charlando el trabajo, nos dimos cuenta de que armar "una sola PC ideal" no terminaba de mostrar bien el criterio de selección: terminás eligiendo lo mejor que entra en el presupuesto y ya, sin tener que justificar mucho. Por eso decidimos dar un paso más y proponer **dos PCs distintas que cumplen el mismo relevamiento de requisitos pero parten de lógicas de compra opuestas**:

- **PC A — Estudio independiente de animación:** un perfil profesional, de una sola persona que vive de esto. Ahí la lógica es "la máquina es la herramienta de trabajo, así que conviene invertir de más porque se recupera en tiempo de render y en vida útil del equipo".
- **PC B — Aula de la facultad (perfil institucional):** el caso de una institución que tiene que comprar 30 equipos iguales con presupuesto limitado. Ahí la lógica se invierte: "alcanza con que cumpla el programa de la materia y nada más", porque cualquier gasto de más se multiplica por 30.

Nos pareció mucho más rico de defender que una sola propuesta, porque ya no es "elegimos lo mejor" sino "elegimos lo adecuado para cada caso", que es justo lo que después se nota en la justificación de cada componente.

## Cómo trabajamos el relevamiento (esto es igual para las dos PCs)

Para las dos propuestas usamos la misma base de requisitos: nos metimos a la web oficial de cada programa para sacar los requisitos recomendados (no los mínimos, como pedía la consigna). En algunos casos como Blender y OBS la info estaba clara, pero con Inkscape y Audacity tuvimos que buscar un poco más en foros y wikis.

La idea para armar cualquiera de las dos PCs es la misma: agarrar el requisito más alto entre todos los programas, en cada categoría (CPU, RAM, GPU, etc.), y a partir de ahí decidir si la propuesta lo **supera** (caso PC A) o simplemente lo **cumple justo** (caso PC B).

De los 6 programas, el programa mas potente y que mejores componentes necesita es **Blender** (por el render 3D, las simulaciones y el compositing). Después viene **OBS Studio** por el tema de codificar video en vivo. Los otros cuatro (Krita, GIMP, Inkscape, Audacity) son livianos en comparación, pero cada uno aporta su requisito particular: Krita/GIMP/Inkscape necesitan buena fidelidad de color, y Audacity necesita baja latencia de audio más que potencia bruta.

## Tabla comparativa

| Software | SO compatible | CPU recomendada | RAM recom. | Almacenamiento | GPU |
|---|---|---|---|---|---|
| Blender | Windows 10/11, macOS, Linux | 8+ núcleos | 32 GB (64 en escenas pesadas) | SSD NVMe para SO/apps + 1-2 TB para proyectos | NVIDIA RTX, 8 GB+ VRAM (CUDA/OptiX) |
| OBS Studio | Windows 10/11, macOS 12+, Linux | 6-8 núcleos (o se descarga en NVENC) | 16 GB | SSD dedicado para grabar | NVIDIA GTX 1660+ / RTX (NVENC) |
| Krita | Windows 10/11, macOS, Linux | Quad-core 4 GHz+ | 16 GB | SSD, 512 GB+ | GPU moderna (Vulkan/Direct3D 11/OpenGL 3.0), mejor si es NVIDIA |
| GIMP | Windows 10/11, macOS, Linux | Multinúcleo 2.5 GHz+ | 8-16 GB | SSD, ~2 GB de instalación | OpenGL 3.3, 512 MB+ VRAM (OpenCL) |
| Inkscape | Windows 10/11, macOS, Linux | Quad-core 2.5 GHz+ (pesa más el single-core) | 8 GB | SSD, ~1 GB | OpenGL 2.0+, ayuda tener 1 GB+ VRAM |
| Audacity | Windows 10/11, macOS, Linux | Dual-core 2 GHz+ | 4 GB | SSD, depende del proyecto | No usa GPU |

### Lo que termina pidiendo el conjunto (el "piso" que ninguna de las dos PCs puede pisar para abajo)

| Recurso | Valor mínimo que tiene que cumplir cualquier propuesta | ¿Por qué programa? |
|---|---|---|
| CPU | 8+ núcleos, multinúcleo potente | Blender |
| RAM | 32 GB | Blender |
| GPU | NVIDIA RTX con 8 GB+ de VRAM | Blender (OptiX) + OBS (NVENC) |
| Almacenamiento | SSD NVMe + disco grande para proyectos | Blender / OBS |
| Monitor / color | Buena cobertura sRGB, ΔE bajo | Krita / GIMP / Inkscape |

Esta tabla es la que usamos como punto de comparación en justificacion.md: PC A pasa este piso por arriba en casi todo, y PC B se queda justo en este piso (con una sola excepción que explicamos ahí, la RAM, por el tema de la crisis de precios de la DDR5).

## Algunas notas que sacamos de cada programa

- **Blender:** entre más núcleos tenga la CPU mejor (render por CPU, física, fluidos, compositing), y una GPU NVIDIA RTX ayuda muchísimo porque acelera el render en Cycles con OptiX. La VRAM es importante porque ahí entran las escenas y texturas pesadas. Recomiendan 32 GB de RAM (64 GB en escenas pesadas) y almacenamiento NVMe rápido más algo de almacenamiento grande para los proyectos.
- **OBS Studio:** depende bastante de a qué resolución/FPS se grabe y qué encoder se use. Si usás NVENC (que tienen las GeForce GTX serie 16 en adelante y las RTX) la codificación se la banca la GPU y no la CPU, entonces podés grabar/transmitir sin que se note tanto en el resto del trabajo.
- **Krita:** pide 16 GB de RAM y una GPU que no sea muy vieja, porque el lienzo se acelera por GPU. Además recomiendan usar tableta gráfica para pintar, cosa que con mouse se hace bastante incómodo.
- **GIMP:** anda mejor con 8-16 GB de RAM, tiene soporte OpenCL para algunos filtros y un SSD ayuda con los tiempos de carga.
- **Inkscape:** acá lo que más importa es el rendimiento de un solo núcleo (no tanto la cantidad), porque carga todo el SVG en memoria. Con 8 GB de RAM va cómodo.
- **Audacity:** es el más liviano de todos, con 4 GB de RAM y un CPU de 2 GHz ya anda bien. Lo que más importa en este caso es tener una buena entrada de audio (micrófono o interfaz), no tanto el hardware de cómputo.

## Sistema operativo elegido: Windows 11 Pro 64-bit (para las dos propuestas)

Los seis programas son multiplataforma (Windows, macOS, Linux), así que la decisión no fue por compatibilidad sino por cuál plataforma le saca mejor jugo al hardware en cualquiera de los dos escenarios:

- Soporte maduro de drivers NVIDIA para CUDA/OptiX (Blender) y NVENC (OBS Studio), con los drivers NVIDIA Studio optimizados para creación de contenido.
- Máxima compatibilidad de periféricos: tabletas gráficas (Wacom), placas de captura, interfaces y micrófonos USB.
- Ecosistema y soporte más amplio para los seis programas y sus complementos.
- En el caso institucional (PC B), Windows Pro además permite gestionar los 30 equipos por dominio/políticas de grupo, algo que pesa cuando hay que administrar un aula entera y no una sola máquina.

Linux corre todo el conjunto y es gratis, pero presenta más fricción con drivers NVIDIA y ciertos periféricos. Queda registrado como alternativa de recorte si apareciera una restricción presupuestaria aún mayor, sobre todo en el caso de PC B donde el ahorro se multiplica por 30 licencias.

## Fuentes

- Blender Foundation — Requirements (blender.org/download/requirements) y GPU Rendering (Manual de Blender).
- OBS Project — System Requirements y documentación de encoders (NVENC).
- Krita — página oficial de descarga / requisitos (krita.org).
- GIMP — documentación oficial (docs.gimp.org) y guías de recursos de sistema.
- Inkscape — guías de requisitos y foros oficiales del proyecto.
- Audacity — System Requirements (manual oficial / wiki).

(Los enlaces específicos consultados se detallan en la sección de justificación y en el repositorio.)