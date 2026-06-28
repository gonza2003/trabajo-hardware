# Conclusiones

## Resumen de lo que hicimos

Para el escenario de estudio multimedia (Audacity, Blender, Inkscape, GIMP, Krita y OBS Studio) decidimos no quedarnos en una sola propuesta de hardware, sino comparar **dos PCs que cumplen el mismo relevamiento de requisitos pero responden a lógicas de compra completamente distintas**:

- **PC A — Estudio independiente de animación:** perfil profesional, un solo usuario que vive de este trabajo. Decisión de fondo: invertir por encima del requisito recomendado, porque ese gasto extra se recupera en tiempo de render y en vida útil del equipo.
- **PC B — Aula institucional (perfil tipo facultad, 30 equipos):** perfil de compra masiva con presupuesto acotado. Decisión de fondo: cumplir el piso de requisitos justo y ni un poco más, porque cualquier exceso se multiplica por 30 unidades.

Nos pareció que esta comparación cuenta una historia más completa que una sola PC "ideal", porque obliga a justificar **por qué se elige más** en un caso y **por qué se elige menos** en el otro, en vez de simplemente mostrar la mejor combinación que entra en un presupuesto fijo.

## Tabla de cumplimiento de requisitos

| Recurso | Piso del conjunto de programas | PC A | PC B |
|---|---|---|---|
| CPU | 8+ núcleos | 12 núcleos / 24 hilos — supera | 6 núcleos / 12 hilos — por debajo a propósito* |
| RAM | 32 GB | 64 GB — supera | 16 GB — por debajo a propósito* |
| GPU / VRAM | RTX, 8GB+ | RTX 5070 Ti, 16GB — supera | RTX 5060, 8GB — cumple justo |
| Almacenamiento | NVMe + disco grande | NVMe 1TB + 2TB + externo 4TB — supera | NVMe 1TB — cumple lo básico |
| Color del monitor | sRGB alto, ΔE bajo | 99% DCI-P3, ΔE&lt;2 calibrado — supera | Monitor estándar sin calibrar — por debajo a propósito* |

*Los tres casos marcados "por debajo a propósito" en PC B son decisiones conscientes de recorte para un contexto institucional con 30 equipos, no errores de relevamiento. Las explicamos una por una en justificacion.md y presupuesto.md.

## Lo que más nos interesa poder transmitir en la defensa

1. **No existe "la mejor PC" en abstracto.** Existe la PC adecuada para un caso de uso. Un estudio profesional y un aula de 30 alumnos tienen necesidades, presupuestos y formas de amortizar el gasto totalmente distintas, aunque tengan que correr exactamente los mismos seis programas.
2. **El contexto cambia la lectura de cada componente.** La RTX 5070 Ti de PC A no es "mejor" que la RTX 5060 de PC B en términos absolutos de la consigna — las dos cumplen el requisito (RTX, 8GB+ VRAM). La diferencia es cuánto margen por arriba del piso tiene sentido pagar en cada contexto.
3. **Multiplicar por 30 cambia las decisiones.** Una diferencia de $300.000-400.000 por equipo entre "cumplir justo" y "tener margen" se vuelve una diferencia de 9-12 millones de pesos en una compra institucional. Eso es lo que justifica que en PC B nos hayamos quedado en el piso de RAM, CPU y monitor.
4. **El contexto de mercado también es parte de la justificación técnica.** La crisis de precios de la memoria DDR5 (que detallamos en presupuesto.md) es un dato real de junio de 2026 que afecta directamente la decisión de cuánta RAM poner en cada propuesta, sobre todo en PC B.

## Costo final

| | PC A (1 equipo) | PC B (1 equipo) | PC B × 30 equipos |
|---|---|---|---|
| Total | ≈ $8.420.000 | ≈ $2.420.000 | ≈ $72.600.000 |

La diferencia de costo por equipo (casi 3.5 veces más cara la PC A) refleja fielmente la diferencia de filosofía: en PC A cada componente fue elegido para maximizar productividad de un usuario que rentabiliza la inversión con su propio trabajo; en PC B cada componente fue elegido para que la institución pueda pagar 30 unidades sin resignar que los alumnos puedan cursar la materia con normalidad.

## Limitaciones y consideraciones

- **Precios volátiles:** el costo en Argentina depende del tipo de cambio, impuestos y promociones; los valores son de referencia (junio 2026) y deben confirmarse antes de comprar.
- **La RAM en particular puede seguir moviéndose:** la crisis de precios de la DDR5 es un fenómeno reciente y los analistas no se ponen de acuerdo en cuándo se va a normalizar (algunos hablan de fines de 2026, otros de 2027-2028), así que el presupuesto de ambas PCs podría variar bastante en poco tiempo.
- **Benchmarks orientativos:** los números de rendimiento que se mencionan en la justificación dependen de la configuración específica de cada equipo (drivers, límites de potencia, etc.) y deben tomarse como referencia general.
- **Alternativa Linux:** si se buscara reducir costos de licencias, sobre todo en PC B donde se multiplican por 30, Linux corre todo el conjunto de programas, a cambio de mayor fricción con drivers NVIDIA y la gestión por dominio que ofrece Windows Pro.

## Cierre

Con este enfoque comparativo creemos que mostramos algo más completo que una propuesta única: dos soluciones de hardware igualmente válidas y bien justificadas, cada una coherente con el contexto de uso que tiene que cubrir. La defensa que nos interesa dar no es "elegimos los mejores componentes", sino "supimos elegir qué tan lejos del piso de requisitos conviene ir en cada situación, y por qué".