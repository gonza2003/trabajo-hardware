# Etapa 2 — Selección y justificación de hardware

**Plataforma que elegimos:** AMD AM5 (DDR5, PCIe 5.0)

La elegimos porque es la plataforma actual de AMD, tiene buena relación precio/rendimiento en multinúcleo (que es justo lo que necesita Blender) y en Argentina se consigue bastante bien.

## Criterios que usamos para armar la PC

1. Que cumpla o supere el requisito más alto de todo el combo de programas (lo vimos en requisitos.md).
2. Priorizar GPU y monitor por sobre el resto, porque en este escenario son los componentes que más impactan: la GPU para render acelerado y el monitor para la fidelidad de color.
3. Que todos los componentes sean de la misma plataforma (AM5) para no tener problemas de compatibilidad y poder upgradear después sin cambiar todo.
4. Pensar en que la PC va a estar prendida horas haciendo renders, entonces el tema térmico y el ruido también importan.

## 1. CPU — AMD Ryzen 9 7900 (12 núcleos / 24 hilos)

**Specs:** 12c/24t, 3.7 GHz base / 5.4 GHz boost, 65W de TDP, socket AM5, viene con gráficos integrados Radeon, soporta hasta 128 GB de RAM y tiene 24 líneas PCIe 5.0.

**Por qué la elegimos:** Blender escala casi al palo con la cantidad de hilos que tenga la CPU, tanto en render por CPU como en simulaciones de física/fluidos y en compositing. Pasar de 8 a 12 núcleos / 24 hilos se nota bastante en escenas pesadas, y también ayuda si querés renderizar y al mismo tiempo seguir trabajando en Krita/GIMP o grabando con OBS. Como tiene solo 65W de TDP, se puede enfriar con un cooler más chico y hace menos ruido. La gráfica integrada también suma porque si algún día falla la GPU dedicada, la PC sigue prendiendo y se puede usar para lo básico. En Cinebench R23 multi-core anda cerca de los 28.900 puntos, prácticamente al lado del 7900X que es más caro.

**Alternativa más barata:** Ryzen 7 7700 (8c/16t), que ya viene con cooler incluido (Wraith Stealth). Cumple el mínimo de 8+ núcleos y te ahorra comprar un disipador aparte.

## 2. Motherboard — MSI MAG B650 Tomahawk WiFi

**Specs:** chipset B650, socket AM5, soporta DDR5 hasta 6400+ con overclock, dos M.2 PCIe 4.0, USB 3.2 Gen 2x2, LAN de 2.5G, Wi-Fi 6E y un VRM bastante reforzado.

**Por qué la elegimos:** el VRM reforzado le da margen para alimentar un Ryzen 9 de 12 núcleos sin sufrir en cargas largas de render. El Wi-Fi 6E y la LAN 2.5G ayudan para subir proyectos pesados o transmitir en vivo. Tener dos slots M.2 también deja la puerta abierta para meter más almacenamiento NVMe el día de mañana.

**Alternativas:** Gigabyte B650 Gaming X AX V2 (más barata) o ASUS ProArt B650-Creator si se quiere algo más orientado a "creator" (tiene USB4 y doble LAN).

## 3. RAM — 32 GB (2x16 GB) DDR5-6000 CL36

32 GB es lo mínimo que pide Blender para escenas pesadas, y también es necesario para poder tener abierto Krita + GIMP + OBS + el navegador sin que la PC empiece a usar memoria virtual (swap). Elegimos justo la frecuencia 6000 MHz porque en los Ryzen 7000 es el punto donde mejor rinde el Infinity Fabric con los perfiles AMD EXPO activados — básicamente, más velocidad de RAM en esta plataforma se traduce en mejor rendimiento general, no es solo para gamers. Va en doble canal, 2 módulos de 16 GB cada uno.

## 4. Almacenamiento — SSD NVMe 1TB + HDD 2TB

- SSD: WD Blue SN580 1TB NVMe Gen4 (~4150 MB/s, 600 TBW, 5 años de garantía)
- HDD: Seagate Barracuda 2TB SATA III 7200rpm (256MB de caché)

El SSD NVMe es para que Windows 11 arranque rápido, los proyectos carguen al toque y para que Blender/OBS puedan usarlo de caché. El HDD de 2TB es para el almacenamiento masivo, que en este escenario se llena rápido porque OBS genera archivos de video enormes, y también para guardar librerías de assets y backups. Es más barato por GB que un SSD grande.

## 5. GPU — NVIDIA GeForce RTX 5060 Ti 16GB (ASUS Prime OC)

**Specs:** arquitectura Blackwell, 16GB de GDDR7, RT Cores, NVENC de novena generación (soporta AV1/HEVC/H.264), PCIe 5.0, pide una fuente de 600W como mínimo.

Esta es la pieza central de toda la propuesta porque:

- **Blender (OptiX):** Blender usa OptiX para aprovechar el ray-tracing por hardware que tienen las placas RTX y así renderizar más rápido en Cycles. Comparando con la RTX 4060 Ti (la generación anterior), esta tarjeta rinde como un 12,6% más en los benchmarks de Blender Open Data.
- **OBS Studio (NVENC):** el encoder NVENC que trae la placa se encarga de codificar el video por su cuenta, sin tocar la CPU. Esto significa que mientras grabás o transmitís con OBS, la CPU queda libre para seguir laburando en Blender o Krita. Las RTX de series 40 y 50 también soportan codificación en AV1, que es más eficiente que el H.264 de siempre.
- **16GB de VRAM:** da margen de sobra para escenas 3D complejas, texturas en 4K y lienzos grandes en Krita (que también usa la GPU para acelerar el dibujo).

**Alternativa:** la RTX 4060 Ti 16GB sale parecido pero es la generación anterior, así que conviene directamente ir por la 5060 Ti. Si el uso fuera mayormente 2D se podría bajar a una RTX 5060 de 8GB para ahorrar plata.

## 6. Gabinete — Mid-tower ATX con frente de malla

Elegimos uno con frente mesh (rejilla) porque deja entrar mucho más aire, y en este armado la CPU y la GPU van a estar trabajando a full por horas cuando se esté renderizando. Tiene espacio de sobra para una GPU de doble slot, el cooler de torre que elegimos y discos extra si se necesitan más adelante.

## 7. Fuente — CoolerMaster MWE Gold 750 V3 (80 Plus Gold, ATX 3.1)

La RTX 5060 Ti pide 600W de fuente como mínimo. Sumando el Ryzen 9 7900 (que solo consume 65W) y dejando margen para picos de consumo y una futura GPU más potente, 750W con certificación 80+ Gold nos da una eficiencia de casi 90% a carga típica, además de estabilidad y poco ruido. Al ser ATX 3.1 con el conector 12V-2x6, es compatible con las GPU de generaciones actuales sin necesidad de adaptadores raros.

## 8. Refrigeración — Thermalright Peerless Assassin 120 SE

Es un cooler de aire de doble torre con 6 heatpipes y dos ventiladores. Lo elegimos porque mantiene al Ryzen 9 7900 fresco incluso en renders largos, y sale mucho más barato que una refrigeración líquida (AIO), sin el riesgo de que se pinche una manguera o se rompa la bomba con el tiempo.

*Nota: si en la variante económica se usa el Ryzen 7 7700, este ítem se puede sacar porque esa CPU ya viene con cooler de fábrica.*

## 9. Monitor — ASUS ProArt PA278QV 27" QHD IPS

**Specs:** 27 pulgadas, panel IPS, resolución QHD (2560x1440), 350 cd/m² de brillo, 75Hz, soporte ajustable en altura/inclinación/giro/pivote.

Para trabajar en GIMP, Krita e Inkscape la fidelidad de color es tan importante como tener una buena GPU. Este monitor viene calibrado de fábrica y certificado con Calman, con un ΔE menor a 2 y 100% de cobertura sRGB y Rec.709 — básicamente, los colores que ves en pantalla son los reales. La resolución QHD también da más espacio en pantalla para tener varios paneles abiertos o ver mejor el viewport de Blender, y el pivote (poder girar el monitor a vertical) es útil para ilustrar.

## 10. Periféricos

- **Tableta gráfica - Wacom Intuos Small (Bluetooth):** la recomendamos para Krita y para retocar en GIMP. Tiene 4096 niveles de presión, lo que permite controlar el grosor y la opacidad del trazo de forma mucho más natural que con un mouse.
- **Micrófono - FIFINE K669/K681 USB:** es un condensador cardioide plug & play por USB, sirve tanto para grabar voz en Audacity como para narrar/transmitir con OBS, sin necesitar una interfaz de audio aparte.
- **Webcam - Logitech C920 Full HD:** la elegimos porque graba en 1080p a 30 fps, tiene enfoque automático y corrección de luz, y es el "estándar" que se usa hace años para esto, tanto para hacer la presentación audiovisual del propio trabajo como para usarla de fuente en OBS Studio (por ejemplo si se quiere grabar la cara en una esquina mientras se muestra la pantalla, algo típico en tutoriales o streams). Las webcams 4K más nuevas casi duplican el precio y para este uso no se justifica el salto.
- **Parlantes - Logitech Z207 (estéreo, con Bluetooth):** los pensamos para escuchar de forma decente lo que se está editando en Audacity o el audio del video que se está armando en OBS/Blender, sin tener que depender de auriculares todo el tiempo. No hace falta ir a un sistema de monitores de estudio (esos arrancan en varios cientos de miles de pesos más caros y están pensados para mezclar audio profesionalmente, algo que excede lo que pide este escenario); con un 2.0 estéreo decente alcanza de sobra para chequear el resultado de una edición.
- **Teclado + mouse - Logitech MK270 (inalámbrico):** un combo simple y confiable, no hace falta gastar más ahí porque el presupuesto importante va para GPU, monitor y tableta.
- **Mouse 3D - 3Dconnexion SpaceMouse Compact:** este fue el más difícil de resolver porque la línea SpaceMouse es cara incluso en su versión más chica (la Compact, que es la de entrada de toda la familia). La descartamos en su versión "Pro" o "Wireless" porque ahí ya estamos hablando de un producto pensado para estudios de diseño profesional, no para un estudiante. Nos quedamos con la **Compact** (la más básica de la línea, con cable y 2 botones) porque igual permite lo importante: navegar en 3D con una mano (paneo, zoom y rotación en Blender) mientras con la otra mano se sigue usando el mouse normal para seleccionar y modelar. Es la versión más accesible dentro de un producto que de por sí es un nicho caro, y para nuestro escenario (un estudiante armando un estudio multimedia, no un estudio de animación profesional) nos pareció el punto justo entre "tenerlo" y "gastar una fortuna en algo que se usa ocasionalmente".
- **Sistema operativo - Windows 11 Pro 64-bit:** ya lo justificamos en requisitos.md, soporta bien CUDA/OptiX y NVENC con los drivers NVIDIA Studio.

## Por qué todo es plataforma AM5

Elegimos que CPU, motherboard y RAM compartan el mismo ecosistema (AM5 + DDR5 + PCIe 5.0) para asegurar compatibilidad total entre todo, y además dejamos abierta una ruta de actualización a futuro: se podría poner una CPU más nueva, agregar un segundo SSD NVMe o subir de GPU sin tener que cambiar la motherboard ni la RAM.