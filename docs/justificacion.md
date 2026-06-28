# Etapa 2 — Selección y justificación de hardware

## La decisión de fondo: dos PCs, dos filosofías de compra

Como explicamos en requisitos.md, decidimos comparar dos propuestas en vez de presentar una sola, porque representan dos formas opuestas de pensar la misma compra:

- **PC A — Estudio independiente de animación:** perfil profesional, un solo usuario que produce y vende su propio trabajo. La lógica acá es "la máquina es la herramienta de laburo, invertir de más se paga solo en tiempo de render y en vida útil del equipo".
- **PC B — Aula de la facultad (perfil institucional):** alguien que compra 30 equipos iguales con presupuesto acotado para que los alumnos cursen una materia. La lógica se invierte: "tiene que cumplir el programa de la materia y nada más", porque cualquier gasto de más se multiplica por 30 y la máquina no la usa un profesional que rentabiliza la inversión, sino que rota entre decenas de estudiantes.

Las dos parten del mismo piso de requisitos (el de requisitos.md), pero una lo supera bastante y la otra se queda justo en el límite. Vamos componente por componente mostrando las dos elecciones en paralelo.

## Criterios generales

1. Las dos PCs tienen que cumplir como mínimo el requisito más exigente del conjunto de programas (8+ núcleos, 32GB RAM, RTX 8GB+ VRAM, SSD NVMe, buena fidelidad de color).
2. En PC A, directamente vamos por superar ese piso en casi todo, porque el costo extra se justifica en productividad de un solo usuario profesional.
3. En PC B, el objetivo es no pasarse de ese piso salvo que sea estrictamente necesario, porque cada peso de más se multiplica por 30 equipos.
4. Las dos plataformas elegidas son AMD AM5 (DDR5, PCIe 5.0), por ser la plataforma actual y la de mejor relación precio/rendimiento multinúcleo en Argentina.

## 1. CPU

| | PC A — Estudio profesional | PC B — Aula institucional |
|---|---|---|
| Modelo | AMD Ryzen 9 9900X (12c/24t) | AMD Ryzen 5 7600 (6c/12t, con cooler incluido) |
| Specs | 4.4 GHz base / 5.6 GHz boost, 120W TDP, AM5, Zen 5 | 3.8 GHz base / 5.1 GHz boost, 65W TDP, AM5, Zen 4 |

**PC A:** vamos directo a un Ryzen 9 de generación actual porque Blender escala casi linealmente con la cantidad de hilos (render por CPU, simulación de física/fluidos, compositing). Para un estudio que vive de esto, tener 12 núcleos en vez de los 8 mínimos requeridos significa renderizar más rápido y poder seguir trabajando en otra cosa mientras corre un render en segundo plano — eso es tiempo (y plata) que se recupera.

**PC B:** el Ryzen 5 7600 cumple el piso de 8+ núcleos... en realidad tiene 6 núcleos / 12 hilos, que es menos que el mínimo recomendado de Blender. Lo elegimos a propósito como ejemplo del tipo de recorte que se hace en un contexto institucional: en un aula, los alumnos no están renderizando escenas de producción todo el día, sino aprendiendo a usar el programa con proyectos chicos de práctica. El Ryzen 5 ya viene con cooler de fábrica (ahorra esa compra) y, multiplicado por 30 equipos, la diferencia de precio contra un Ryzen 9 es enorme.

## 2. Motherboard

| | PC A | PC B |
|---|---|---|
| Modelo | MSI MAG X870 Tomahawk WiFi | Placa B650 de gama de entrada (ej. MSI PRO B650M-A o Gigabyte B650M) |

**PC A:** el chipset X870 da más líneas PCIe 5.0, mejor VRM (importante para bancar 12 núcleos en cargas largas de render) y conectividad más moderna (USB4, Wi-Fi 7 en algunos modelos).

**PC B:** una B650 micro-ATX de gama de entrada cumple sin problema lo que necesita un Ryzen 5 7600, y al comprar 30 unidades cada componente "de gama media" que se pueda bajar a "gama de entrada" representa un ahorro importante en el total.

## 3. RAM

| | PC A | PC B |
|---|---|---|
| Configuración | 64 GB (2x32) DDR5-6000 | 16 GB (2x8 o 1x16) DDR5-6000 |

**PC A:** Blender recomienda 64 GB para escenas pesadas, y para un estudio profesional que puede recibir cualquier tipo de encargo (desde animaciones cortas hasta proyectos grandes con muchas capas y texturas 4K) conviene no quedarse corto.

**PC B:** acá está el cambio más importante que tuvimos que hacer respecto del relevamiento de requisitos, y lo dejamos marcado a propósito porque nos pareció un buen punto para defender: el requisito recomendado de Blender es 32 GB, pero **decidimos bajar a 16 GB en la propuesta institucional por la crisis de precios de la memoria DDR5**. Desde fines de 2025 el precio mundial de la RAM DDR5 subió entre 3 y 5 veces por la demanda de los centros de datos de IA, y en Argentina hoy (junio 2026) un kit de 32 GB DDR5-6000 ronda los $630.000-680.000, mientras que un kit de 16 GB anda cerca de los $330.000 (ver fuentes en presupuesto.md). Multiplicado por 30 equipos, ir a 32 GB en vez de 16 GB significa gastar entre 9 y 10 millones de pesos extra solo en memoria. Para un aula donde los alumnos hacen ejercicios de práctica (no producción real), nos pareció razonable priorizar que la institución pueda comprar los 30 equipos completos por sobre cumplir al pie de la letra el requisito recomendado de RAM. Lo anotamos como la excepción consciente al "piso" de requisitos.

## 4. Almacenamiento

| | PC A | PC B |
|---|---|---|
| Configuración | SSD NVMe 1TB (SO/apps) + SSD NVMe 2TB (proyectos) + disco externo 4TB de respaldo | 1 solo SSD NVMe 1TB |

**PC A:** doble NVMe porque un estudio profesional necesita separar el sistema/apps de los proyectos pesados, y el disco externo es para respaldo — perder un proyecto de un cliente por no tener backup es un problema serio cuando es tu fuente de ingreso.

**PC B:** un solo SSD alcanza de sobra para los seis programas y los proyectos de práctica de los alumnos. No tiene sentido sumar un segundo disco ni un externo: el respaldo de los trabajos de los alumnos lo maneja la red/servidor de la facultad, no el equipo individual.

## 5. GPU

| | PC A | PC B |
|---|---|---|
| Modelo | NVIDIA RTX 5070 Ti 16GB | NVIDIA RTX 5060 8GB |

**PC A:** la RTX 5070 Ti da mucho margen de VRAM (16GB) para escenas 3D complejas y texturas pesadas, y acelera de sobra tanto Blender (OptiX) como OBS (NVENC). Para un estudio que compite por velocidad de entrega, esta es la pieza donde más vale la pena gastar.

**PC B:** la RTX 5060 8GB cumple el piso exacto del requisito (RTX, 8GB+ VRAM) ni un poco más. Sostiene bien NVENC para OBS y OptiX para Blender en proyectos chicos de aula, que es todo lo que un alumno de la materia necesita.

## 6. Gabinete, fuente y refrigeración

| | PC A | PC B |
|---|---|---|
| Gabinete | Mid-tower ATX mesh, gama media-alta | Mid-tower ATX mesh, gama de entrada |
| Fuente | 850W 80 Plus Gold | 650W 80 Plus Bronze/Gold |
| Refrigeración | Cooler de aire doble torre (o AIO 240mm) | Cooler incluido de fábrica con el Ryzen 5 7600 |

En PC A buscamos margen térmico y silencio para renders largos y sostenidos. En PC B, al usar una CPU de bajo consumo que ya trae su propio cooler, no hace falta gastar en refrigeración aparte, y una fuente más chica alcanza sin problema porque la GPU consume mucho menos que la RTX 5070 Ti.

## 7. Monitor

| | PC A | PC B |
|---|---|---|
| Modelo | ASUS ProArt PA279CRV 27" 4K (99% DCI-P3, ΔE&lt;2, calibrado de fábrica) | Monitor 24"-27" FHD/QHD IPS estándar, sin calibración de color |

**PC A:** para un estudio que vende su trabajo, la fidelidad de color no es un lujo sino una condición de calidad: el cliente final va a ver el resultado en otra pantalla, y si la del estudio no es fiel, el color "se rompe" en la entrega.

**PC B:** un monitor IPS común, sin pretensiones de calibración profesional, es perfectamente suficiente para que un alumno aprenda a usar Krita, GIMP o Inkscape. Pagar por calibración de fábrica en 30 monitores de aula sería gastar en algo que el caso de uso no necesita.

## 8. Periféricos

| | PC A | PC B |
|---|---|---|
| Tableta gráfica | Wacom Intuos Pro Medium (Bluetooth, 8192 niveles de presión) | No incluida |
| Mouse 3D | 3Dconnexion SpaceMouse Compact | No incluido |
| Teclado + mouse | Combo de gama media | Combo básico |
| Webcam / micrófono | Opcionales según necesidad de cada proyecto | No incluidos |

**PC A:** acá entra todo lo que es "típico de un animador de Blender profesional". La tableta buena hace una diferencia real en la velocidad de trabajo en Krita, y el mouse 3D permite navegar en 3D con una mano mientras la otra sigue en el mouse normal, algo que un estudio que factura por proyecto entregado puede justificar rápido.

**PC B:** ninguno de los dos se justifica para alumnos que recién están aprendiendo. Un mouse 3D en un aula de 30 PCs prácticamente no se usaría (es una herramienta de productividad para alguien que ya domina el software), y lo mismo con una tableta de nivel profesional — si en algún momento se necesitara para una clase puntual de ilustración, conviene comprar unas pocas tabletas compartidas en vez de equipar las 30 PCs.

## Coherencia de cada propuesta

Lo que tratamos de mostrar con esta comparación es que ninguna de las dos PCs es "mejor" en abstracto: **cada una es coherente con el perfil de uso que tiene que cubrir**. PC A invierte en todo lo que acelera el trabajo de un profesional porque ese gasto se recupera. PC B se mantiene en el piso de los requisitos porque cualquier exceso se multiplica por 30 y no hay un solo usuario que rentabilice esa inversión extra. Esa es la idea que más nos interesa poder explicar bien en la defensa.