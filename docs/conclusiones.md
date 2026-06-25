# Conclusiones

## Resumen de lo que hicimos

Armamos una propuesta de estación de trabajo para un estudio multimedia que pueda correr sin problemas (y hasta al mismo tiempo) Audacity, Blender, Inkscape, GIMP, Krita y OBS Studio. Para llegar a esto, primero relevamos los requisitos recomendados de cada programa, vimos cuál era el "techo" de exigencia entre todos (que terminó siendo Blender, seguido de OBS) y a partir de ahí elegimos los componentes que cumplan o superen ese techo, todo corriendo sobre Windows 11 Pro 64-bit.

## Las decisiones más importantes que tomamos

1. **GPU NVIDIA RTX 5060 Ti 16GB** — sin duda la elección más importante de todo el armado. Permite usar OptiX para acelerar el render en Blender (Cycles) y NVENC para que OBS codifique video sin tocar la CPU. Los 16GB de VRAM dan bastante margen para escenas 3D pesadas y texturas grandes.
2. **CPU Ryzen 9 7900 (12c/24t)** — porque tanto el render por CPU como las simulaciones y el compositing de Blender escalan con la cantidad de hilos. Con 12 núcleos se puede renderizar y seguir trabajando al mismo tiempo sin que la PC se trabe.
3. **32GB de RAM DDR5-6000** — es lo mínimo que pide Blender para escenas pesadas, y la frecuencia que elegimos es la que mejor rinde en la plataforma Ryzen 7000.
4. **Monitor ASUS ProArt PA278QV** (100% sRGB, ΔE menor a 2) — nos dimos cuenta de que para este escenario la fidelidad de color es casi tan importante como la potencia de cómputo, porque se va a usar para diseño en Krita, GIMP e Inkscape.
5. **Plataforma AM5** — la elegimos por ser actual, coherente entre todos los componentes y porque deja la puerta abierta para actualizar la PC más adelante (DDR5, PCIe 5.0).

## Tabla de cumplimiento de requisitos

| Recurso | Requisito máximo del conjunto | Lo que propusimos | ¿Cumple? |
|---|---|---|---|
| CPU | 8+ núcleos | 12 núcleos / 24 hilos | Sí, lo supera |
| RAM | 32 GB | 32 GB DDR5-6000 | Sí, cumple |
| GPU / VRAM | RTX, 8GB+ | RTX 5060 Ti, 16GB | Sí, lo supera |
| Almacenamiento | NVMe + disco grande | NVMe 1TB + HDD 2TB | Sí, cumple |
| Color del monitor | sRGB alto, ΔE bajo | 100% sRGB, ΔE < 2 | Sí, cumple |

Como se ve, en CPU y en GPU/VRAM la propuesta queda por encima de lo mínimo pedido, lo que le da margen para que la PC no quede obsoleta tan rápido y aguante proyectos más grandes en el futuro.

## Costo y posibilidad de escalar

El sistema completo (la PC + monitor + periféricos + el sistema operativo) sale aproximadamente $4.000.000 ARS, donde la GPU (~25%) y el monitor (~15%) son los rubros que más pesan. También armamos una variante más económica (~$3.500.000 ARS) que mantiene la RAM, la VRAM y el SSD sin tocar, pensada para el caso de que hubiera un límite de presupuesto más ajustado. Como toda la plataforma es AM5, en el futuro se podría poner una CPU mejor, agregar un segundo SSD NVMe o cambiar a una GPU más potente sin necesidad de cambiar la motherboard ni la RAM.

## Algunas limitaciones que encontramos

- **Los precios cambian todo el tiempo:** en Argentina el costo del hardware depende mucho del dólar, los impuestos y las promociones de cada momento. Los precios que usamos son de referencia (junio 2026).
- **Los benchmarks son orientativos:** los números que citamos (Cinebench, Blender Open Data) dependen de cómo esté configurada cada PC (límites de potencia, PBO, drivers), así que hay que tomarlos con pinzas y no como un valor exacto.
- **La opción de Linux:** si en algún momento se buscara bajar el costo sacando la licencia de Windows, Linux también puede correr todo el combo de programas, aunque con más complicaciones con los drivers de NVIDIA y algunos periféricos.

## Cierre

Con esta propuesta llegamos a una PC bastante equilibrada y pensada específicamente para producción multimedia: aprovechamos la aceleración por hardware de NVIDIA en los programas que la soportan, priorizamos la fidelidad de color para el trabajo visual, y tratamos de mantener un costo razonable dejando una ruta clara para actualizar la PC en el futuro. Creemos que con esto cumplimos lo que pedía la consigna: un relevamiento de requisitos completo, una justificación técnica con sentido y un presupuesto detallado y verificable.