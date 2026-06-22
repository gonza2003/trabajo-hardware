# Selección y Justificación de Hardware

En base al relevamiento de requisitos que hicimos para los programas del **Tema 2 (Estudio Multimedia)**, diseñamos una configuración equilibrada y potente. Nos enfocamos principalmente en cumplir con los 32 GB de RAM que pide *Blender* y una buena placa de video que nos sirva tanto para los renderizados como para el procesamiento de *OBS Studio*.

A continuación, detallamos componente por componente con su precio de referencia en el mercado argentino y la justificación técnica de la elección.

---

### 1. Procesador (CPU)
* **Componente:** AMD Ryzen 7 5700X (8 Núcleos / 16 Hilos, hasta 4.6 GHz)
* **Precio de referencia:** $340.400 ARS (Fuente: Compra Gamer)
* **Justificación técnica:** Elegimos este procesador porque tanto *Blender* como *OBS Studio* exigen CPUs multi-núcleo para renderizar escenas complejas y procesar streams en vivo en simultáneo. Al contar con 8 núcleos reales y 16 hilos, cumplimos sobradamente con los requisitos recomendados. Además, como el fabricante aclara que **no incluye cooler de fábrica**, esta elección justifica que hayamos sumado un disipador de torre Deepcool por separado en el presupuesto para evitar el estrangulamiento térmico (*thermal throttling*).

### 2. Memoria RAM
* **Componente:** Corsair Vengeance LPX 32GB (2 x 16GB) DDR4 3200MHz
* **Precio de referencia:** $110.000 ARS (Fuente: Mexx)
* **Justificación técnica:** Fuimos directo por un kit de 32 GB porque es el requisito recomendado que exige *Blender* para manejar escenas 3D complejas sin quedarse sin memoria. Además, programas como *GIMP* y *Krita* consumen muchísima RAM cuando trabajás con lienzos enormes o muchas capas. Al poner dos módulos de 16 GB activamos el *Dual-Channel*, lo que duplica la velocidad de comunicación entre la memoria y el procesador, dándonos más fluidez.

### 3. Tarjeta Gráfica (GPU)
* **Componente:** MSI NVIDIA GeForce RTX 4060 8GB GDDR6
* **Precio de referencia:** $490.000 ARS (Fuente: Hard Gamers)
* **Justificación técnica:** Este componente es clave para el diseño multimedia. Elegimos NVIDIA porque cuenta con tecnologías específicas para este tipo de laburo:
* Para **Blender**: Aprovecha los núcleos *RTX* y la tecnología *OptiX* para renderizar por hardware muchísimo más rápido que usando solo el procesador, cumpliendo con los 8 GB de VRAM recomendados.
* Para **OBS Studio**: Incorpora el codificador *NVENC* de NVIDIA, lo que significa que la placa de video se encarga de procesar el stream de video de forma nativa, liberando de carga a la CPU para que no colapse.

### 4. Almacenamiento (SSD)
* **Componente:** SSD NVMe PCIe M.2 Kingston NV2 1TB
* **Precio de referencia:** $85.000 ARS (Fuente: Compra Gamer)
* **Justificación técnica:** Como investigamos en los requisitos, *Audacity* e *Inkscape* necesitan discos locales rápidos y estables porque trabajar desde nubes o un USB puede romper los archivos o ralentizar el flujo de trabajo. Un SSD NVMe es hasta 5 veces más rápido que un SSD común (SATA), lo que nos garantiza que los archivos pesados de audio y video se abran al toque y que el caché de pinceles en *Krita* no tenga *lag*.

### 5. Placa Madre (Motherboard)
* **Componente:** ASUS PRIME B550M-A AC (PCIe 4.0, Wi-Fi/BT)
* **Precio de referencia:** $263.000 ARS (Fuente: Mercadolibre)
* **Justificación técnica:** Elegimos una motherboard con chipset B550 porque soporta de forma nativa el procesador Ryzen 7 que elegimos y tiene soporte para PCIe 4.0, lo que exprime al máximo la velocidad del SSD Kingston y la placa RTX 4060. Además, este modelo viene con Wi-Fi integrado, lo cual es un golazo si en el estudio no tenemos una boca de red cerca.

### 6. Fuente de Alimentación
* **Componente:** XPG Pylon 650W 80 Plus Bronze
* **Precio de referencia:** $95.000 ARS (Fuente: Mexx)
* **Justificación técnica:** El consumo estimado de la RTX 4060 y el Ryzen 7 ronda los 400W-450W en máxima carga (renderizando). Elegimos una fuente de 650W para tener un margen de seguridad cómodo. Además, contar con la certificación *80 Plus Bronze* nos asegura que la fuente es eficiente energéticamente y protege los componentes contra bajones o picos de tensión, algo vital para cuidar una inversión tan grande.

### 7. Monitor y Periféricos
* **Componentes:** Monitor LG 24" IPS 75Hz Full HD + Kit Teclado y Mouse Logitech
* **Precio de referencia:** Monitor $190.000 ARS / Periféricos $45.000 ARS (Fuente: MercadoLibre)
* **Justificación técnica:** Para el monitor nos fijamos en la resolución recomendada por *Blender* (1920x1080) y elegimos un panel **IPS**. Los paneles IPS son obligatorios para diseño (*GIMP*, *Krita*, *Inkscape*) porque no distorsionan los colores según el ángulo desde el que mires la pantalla, dando colores reales. El kit Logitech lo elegimos por una cuestión de durabilidad para el tecleo diario.

### 8. Auriculares (Tipo Casco)
* **Componente:** Audio-Technica ATH-M20x (Diseño cerrado de estudio)
* **Precio de referencia:** $95.000 ARS (Fuente: MercadoLibre)
* **Justificación técnica:** Para trabajar de forma profesional en **Audacity**, no podemos usar auriculares comunes de celular porque alteran las frecuencias. Elegimos estos auriculares de monitoreo tipo casco porque ofrecen una respuesta de frecuencia plana y un aislamiento cerrado. Esto nos permite escuchar con total precisión los detalles del audio, detectar ruidos de fondo y ecualizar correctamente sin interferencias externas.

### 9. Cámara Web
* **Componente:** Logitech C920s Pro HD (Resolución 1080p a 30 fps)
* **Precio de referencia:** $85.000 ARS (Fuente: MercadoLibre)
* **Justificación técnica:** Una estación multimedia que utiliza **OBS Studio** para transmisiones en vivo o grabación de video necesita una entrada de imagen nítida. Elegimos esta cámara porque graba en Full HD real, tiene corrección de luz automática y es compatible de forma nativa con OBS. Esto asegura que el stream se vea profesional, fluido y sin pixelarse, liberando además al procesador del trabajo de compresión gracias a su compatibilidad con los formatos de video estándar.

---