# Relevamiento de Requisitos: Estudio Multimedia

Para el desarrollo de este sistema informático profesional, se analizaron los requisitos recomendados del software asignado para el **Tema 2**. El objetivo es garantizar que la estación de trabajo funcione con fluidez absoluta en tareas de edición de audio, modelado 3D, diseño vectorial, manipulación de imágenes y transmisión en vivo.

---

## 📊 Tabla Comparativa de Requisitos Recomendados

A continuación, se consolidan los requisitos óptimos de hardware y software extraídos de la documentación oficial de cada aplicación:

| Software | Sistema Operativo Compatible | CPU Recomendada | Memoria RAM | Almacenamiento Requerido | GPU (Si aplica) |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Audacity** | Windows 10/11 (32/64 bits) | Cualquier CPU compatible con el SO | 4 GB o superior | HDD/SSD local (No nubes ni USB) | No requiere dedicada |
| **Blender** | Windows 11, Linux (64 bits), macOS | Multi-core de 8 núcleos | 32 GB | SSD con espacio para proyectos | 8 GB de VRAM (NVIDIA/AMD) |
| **Inkscape** | Windows 8.1/10/11, macOS, Linux | 1 GHz o superior (Quad-Core) | 8 GB | SSD (Espacio según proyectos) | Integrada moderna o Dedicada |
| **GIMP** | Windows 10/11 (64 bits), macOS, Linux | Intel/AMD Dual-Core o superior | 16 GB | SSD para alta velocidad de lectura | Aceleración por hardware opcional |
| **Krita** | Windows 8.1 o superior, macOS, Linux | CPU moderna de 64 bits | 16 GB | SSD para caché de pinceles | OpenGL 3.0 / Direct3D 11 |
| **OBS Studio**| Windows 11 (64 bits), macOS, Linux | Intel i7 8700k / AMD Ryzen 5 1600X | 8 GB | SSD para grabación local | GTX 10 Series / Radeon 5000 |

---

## 🔍 Análisis Detallado por Software

### 1. Audacity
Es un software gratuito para grabar y editar audios. Es compatible con Windows 10 y 11, así como con versiones anteriores (8.1, 7 y Vista) en arquitecturas de 32 y 64 bits. No posee requisitos específicos de CPU ni GPU y funciona sin problemas en cualquier PC o notebook compatible. El único requisito crítico es contar con un **disco duro o SSD local**, ya que el almacenamiento en red (la nube), discos externos o USB pueden no ser fiables para el flujo de datos en tiempo real.

### 2. Blender
Es una suite de creación 3D gratuita y de código abierto que cubre modelado, animación, renderizado y edición de video. Es multiplataforma (Linux, Windows y macOS) y permite personalización mediante scripts en Python. 
* **En Windows y Linux:** Requiere Windows 11 o distribución con `glibc 2.28` o posterior de 64 bits, un procesador de 8 núcleos, 32 GB de RAM y una GPU con 8 GB de VRAM. 
* **En macOS:** Requiere macOS 12 o superior (como los perfiles de soporte avanzados) y arquitectura Apple Silicon con 32 GB de RAM.
* **Nota visual:** Se recomienda una resolución de pantalla mínima de **1920x1080**.

### 3. Inkscape
Un potente editor gratuito de gráficos vectoriales que utiliza el formato estándar SVG (W3C). 
* **En Windows:** La versión 1.4.x requiere al menos Windows 8.1; versiones anteriores como la 1.2.2 extenden soporte hasta Windows 7, y la 0.92.3 soporta Vista y XP. 
* **En macOS y Linux:** Soporta procesadores Intel y Apple Silicon. En Linux los requisitos de hardware son muy bajos porque el procesamiento de vectores recae principalmente en la CPU (se aconseja 1 GHz o superior y 8 GB de RAM). La mayoría de las placas de video integradas son suficientes.

### 4. GIMP
Editor de imágenes multiplataforma y software libre que soporta múltiples lenguajes de programación para la creación de scripts (C, C++, Python, etc.). 
* **En Windows:** Exige Windows 11 (64 bits) si se descarga desde la Microsoft Store, o Windows 10 mediante su instalador ejecutable (`.exe`). Requiere CPU Intel o AMD de 64 bits de doble núcleo o superior.
* **En macOS y Linux:** Soporta macOS 10.12 o superior (Intel/Apple Silicon) y cualquier distribución moderna de Linux vía Flatpak o gestor de paquetes nativo.
* **Memoria:** Para todos los entornos se establece una memoria RAM recomendada de **16 GB** para trabajar con imágenes complejas de manera fluida.

### 5. Krita
Programa de pintura digital profesional enfocado en ilustradores y artistas conceptuales. Es de código abierto y multiplataforma (Windows 8.1+, macOS 10.14+ y Linux). Demanda un mínimo de 16 GB de RAM recomendados y soporte gráfico para OpenGL 3.0 o superior / Direct3D 11. Como periférico fundamental para el diseño, se aconseja el uso de una **tableta gráfica** compatible.

### 6. OBS Studio
Software libre enfocado en la grabación de video y transmisión en streaming en tiempo real. Posee una API robusta para acoplar complementos a medida.
* **En Windows:** Requiere estrictamente Windows 11 de 64 bits, procesadores Intel Core i7 8700k / AMD Ryzen 5 1600X, 8 GB de RAM y placas gráficas equivalentes a NVIDIA GeForce 10 Series o AMD Radeon 5000 Series.
* **En macOS:** Exige versión 12.5 o superior, CPU Intel Quad-Core o Apple Silicon, y 8 GB de RAM.
* **En Linux:** Soportado oficialmente en distros basadas en Ubuntu 14.04 o superior, requiriendo entorno X11 o Wayland con OpenGL 3.3.

---

## 💻 Sistema Operativo Seleccionado para la Propuesta Final

En base al análisis de requisitos de los programas anteriores, el grupo ha decidido que el sistema informático final utilizará **Windows 11 Home/Pro de 64 bits**.

### Justificación Técnica:
1. **Compatibilidad Absoluta:** Es el único sistema operativo que soporta las versiones más actuales de todo el software analizado de forma nativa sin configuraciones complejas adicionales.
2. **Optimización de Hardware:** Aplicaciones pesadas como *Blender* y *OBS Studio* aprovechan de manera mucho más directa las últimas actualizaciones de drivers de video de marcas como NVIDIA y AMD bajo el ecosistema de Windows, lo que garantiza el rendimiento adecuado en renderizados por hardware y transmisiones estables.
3. **Soporte de Tiendas y Ejecutables:** Permite la instalación directa de suites como GIMP desde su tienda nativa o a través de instaladores robustos independientes de 64 bits.