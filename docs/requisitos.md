# Requisitos recomendados del software (fuentes oficiales)

# Requisitos de tema 2: Estudio multimedia. Programas: Audacity, Blender, Inkscape, GIMP, Krita y OBS Studio.

**Por qué dos PCs:** en vez de proponer una sola configuración, decidimos comparar dos
equipos que cumplen el mismo relevamiento de requisitos pero responden a contextos de uso
distintos: **PC A**, pensada para un estudio independiente de animación (un profesional que
vive de esto), y **PC B**, pensada como una de las PCs de la sala de informática de la
institución (uso compartido, presupuesto acotado). Esto nos permite mostrar no solo qué
hardware cumple los requisitos, sino **por qué conviene ir por encima del recomendado en un
caso y quedarse exactamente en el recomendado en el otro**.

**Regla metodológica:** todos los datos de esta sección provienen exclusivamente de las
páginas **oficiales** de cada proyecto. No se utiliza Wikipedia ni blogs. Cuando un
programa publica una columna explícita de **"Recommended"**, se usa esa columna; cuando
solo publica mínimos o "requisitos básicos", se aclara expresamente.

## 1. Tabla comparativa de requisitos recomendados

| Software | Sistema Operativo | CPU recomendada | RAM | Almacenamiento | GPU | Fuente oficial |
|---|---|---|---|---|---|---|
| **Blender** *(Recommended)* | Windows 10 u 11 (64-bit) | **8 núcleos** | **32 GB** | SSD recomendado | **8 GB VRAM** (NVIDIA GeForce 400+/RTX con drivers NVIDIA) | https://www.blender.org/download/requirements/ |
| **OBS Studio** *(solo requisitos básicos)* | Windows 10 u 11 | 64-bit (depende del encoder) | No especifica (comunidad: 16 GB) | Espacio para grabaciones | GPU compatible **DirectX 10.1** (recom. encoder por HW: NVENC) | https://obsproject.com/kb/system-requirements |
| **Krita** *(Recommended)* | Windows 8.1 / 10 / 11 | CPU multinúcleo moderno | **16 GB** (4 GB mínimo) | SSD recomendado | GPU con **OpenGL 3.0+ / Direct3D 11**; tableta recomendada | https://krita.org/en/download/ |
| **GIMP** *(no publica tabla formal)* | Windows 10/11 64-bit | x86-64 moderno | Cuanta más, mejor | SSD recomendado para swap | Sin GPU dedicada obligatoria | https://www.gimp.org/downloads/ |
| **Inkscape** | Windows 10 (1903+) / 11 64-bit | CPU moderno (**mayormente monohilo**: prima el IPC) | 8 GB cómodo | Modesto | GPU con OpenGL para el canvas | https://inkscape.org/release/ |
| **Audacity** | Windows 10/11 64-bit | "No specific CPU requirements" | "No specific requirements" | **Acceso rápido e ininterrumpido a SSD/HDD (crítico)** | "No specific GPU requirements" | https://www.audacityteam.org/download/windows/ |

## 2. Aclaraciones sobre las fuentes

- **Blender** es el único que publica tabla formal de **recomendados**: OS *Windows 10 or 11*, CPU *8 cores*, RAM *32 GB*, GPU *8 GB VRAM*. Es el componente que fija el techo de exigencia del conjunto.
- **OBS Studio** solo lista requisitos básicos y advierte: *"Having a compatible system does not guarantee that it is capable of streaming or recording."*
- **Audacity** declara: *"Audacity has no specific CPU or GPU requirements... requires fast, uninterrupted access to a hard drive or SSD."*
- **GIMP** no publica tabla de hardware recomendado; su documentación explica cómo dimensionar el *Tile Cache* según la RAM.

## 3. Sistema operativo elegido: Windows 11 Pro 64-bit

Se adopta **Windows 11 Pro 64-bit** para ambas computadoras. Razones técnicas:

1. **Drivers NVIDIA para CUDA / OptiX (Blender):** el render por GPU en Cycles y el denoiser por hardware dependen del ecosistema CUDA, plenamente soportado en Windows.
2. **NVENC en OBS Studio:** la codificación por hardware descarga la compresión de video del CPU a un bloque dedicado de la GPU.
3. **Compatibilidad de periféricos:** drivers de primera clase para tableta **Wacom** y **mouse 3D 3Dconnexion** (clave para PC A).
4. **Edición Pro (no Home):** BitLocker (cifrado de proyectos del cliente), unión a dominio y gestión centralizada (clave para administrar las PCs de la sala de informática).
5. **Compatibilidad universal:** los seis programas corren nativamente en Windows; unificar el SO simplifica soporte y capacitación.