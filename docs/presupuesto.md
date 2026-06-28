# Etapa 2 — Presupuesto

Los precios están en pesos argentinos (ARS) y los relevamos en junio de 2026 directamente en las páginas de las tiendas (FullH4rd, Mexx, MercadoLibre). A diferencia de la primera entrega, esta vez chequeamos precio por precio en los sitios reales en vez de poner una referencia vieja, porque el mercado de hardware en Argentina cambió mucho en los últimos meses (más detalle en la nota sobre la RAM, abajo). Donde no encontramos el precio exacto de un modelo puntual, lo dejamos marcado como estimado, calculado a partir de productos equivalentes que sí encontramos.

## Nota importante: la crisis de precios de la RAM DDR5

Antes de ver los números, hay un dato de contexto que cambia bastante el presupuesto: desde fines de 2025, el precio mundial de la memoria DDR5 se disparó entre 3 y 5 veces por la demanda de los centros de datos que entrenan modelos de IA (le compran la producción a los fabricantes antes de que llegue al mercado de consumo). En Argentina, hoy (junio 2026), un kit de 32 GB DDR5-6000 ronda entre $630.000 y $680.000, y un kit de 16 GB anda cerca de los $330.000. Es la primera vez que la RAM es uno de los componentes más caros de toda la PC, algo que hace 2-3 años hubiera sonado raro. Esto golpea fuerte sobre todo en la propuesta institucional (PC B), donde la diferencia se multiplica por 30 equipos.

## PC A — Estudio independiente de animación (perfil profesional)

| # | Componente | Modelo | Tienda (fuente) | Precio (ARS) |
|---|---|---|---|---|
| 1 | CPU | AMD Ryzen 9 9900X (12c/24t) | FullH4rd | 622.900 |
| 2 | Motherboard | MSI MAG X870 Tomahawk WiFi | FullH4rd (estimado por gama) | 650.000 |
| 3 | RAM | 64 GB (2x32) DDR5-6000 | varias (estimado por escasez DDR5) | 1.300.000 |
| 4 | GPU | RTX 5070 Ti 16GB Gigabyte Windforce OC | FullH4rd | 1.600.000 |
| 5 | SSD NVMe #1 | 1TB Gen4/5 (SO + apps) | FullH4rd (estimado) | 280.000 |
| 6 | SSD NVMe #2 | 2TB Gen4 (proyectos) | FullH4rd (estimado) | 480.000 |
| 7 | Disco externo | HDD externo 4TB (respaldo) | MercadoLibre (estimado) | 320.000 |
| 8 | Gabinete | Mid-tower ATX mesh, gama media-alta | FullH4rd (estimado) | 140.000 |
| 9 | PSU | 850W 80 Plus Gold | FullH4rd (estimado) | 230.000 |
| 10 | Refrigeración | Cooler doble torre / AIO 240mm | FullH4rd (estimado) | 230.000 |
| 11 | Monitor | ASUS ProArt PA279CRV 27" 4K | Mexx (estimado por gama, ref. PA278QV $645.289) | 1.300.000 |
| 12 | Tableta gráfica | Wacom Intuos Pro Medium | MercadoLibre (estimado) | 700.000 |
| 13 | Mouse 3D | 3Dconnexion SpaceMouse Compact | MercadoLibre (estimado) | 450.000 |
| 14 | Teclado + mouse | Combo gama media | FullH4rd (estimado) | 80.000 |
| 15 | Sistema operativo | Windows 11 Pro 64-bit | FullH4rd / Activaya (estimado) | 35.000 |

### **TOTAL PC A ≈ $8.417.900 ARS**

Capaz al leer el precio cualquier persona se asusta, pero tiene sentido: ahora estamos comparando contra un perfil exigente de verdad (estudio profesional que supera bastante el requisito recomendado), no contra una PC "intermedia". Los rubros que más pesan son GPU, monitor y RAM — justo los tres componentes donde decidimos ir por encima del piso de requisitos.

## PC B — Aula institucional (perfil tipo facultad, 30 equipos)

| # | Componente | Modelo | Tienda (fuente) | Precio (ARS) |
|---|---|---|---|---|
| 1 | CPU | AMD Ryzen 5 7600 (6c/12t, con cooler) | FullH4rd | 310.000 |
| 2 | Motherboard | B650 gama de entrada (ej. MSI PRO B650M-A) | FullH4rd (estimado) | 280.000 |
| 3 | RAM | 16 GB DDR5-6000 | varias (ref. mercado, ver nota DDR5) | 330.000 |
| 4 | GPU | RTX 5060 8GB Gigabyte Eagle OC | FullH4rd | 700.000 |
| 5 | SSD NVMe | 1TB | FullH4rd (estimado) | 280.000 |
| 6 | Gabinete | Mid-tower ATX, gama de entrada | FullH4rd (estimado) | 110.000 |
| 7 | PSU | 650W 80 Plus Bronze/Gold | FullH4rd (estimado) | 150.000 |
| 8 | Monitor | 24"-27" FHD/QHD IPS estándar | FullH4rd / Mexx (estimado) | 180.000 |
| 9 | Teclado + mouse | Combo básico | FullH4rd (estimado) | 45.000 |
| 10 | Sistema operativo | Windows 11 Pro 64-bit | FullH4rd / Activaya (estimado) | 35.000 |

### **TOTAL POR EQUIPO ≈ $2.420.000 ARS**

### **TOTAL × 30 EQUIPOS ≈ $72.600.000 ARS**

Ahí está el punto que más nos sirve para la defensa: en un contexto institucional, cada decisión de "subir un poco la gama" se multiplica por 30. Por ejemplo, si en vez de 16 GB hubiéramos puesto los 32 GB que recomienda Blender, solo en RAM el gasto adicional habría sido de unos $300.000 por equipo — **9 millones de pesos extra** en el total de los 30 equipos. Esa cuenta es la que justifica por qué en PC B nos quedamos en el piso justo de los requisitos en vez de superarlos como en PC A.

## Comparación rápida

| Rubro | PC A (1 equipo) | PC B (1 equipo) | PC B × 30 |
|---|---|---|---|
| CPU | 622.900 | 310.000 | 9.300.000 |
| GPU | 1.600.000 | 700.000 | 21.000.000 |
| RAM | 1.300.000 | 330.000 | 9.900.000 |
| Monitor | 1.300.000 | 180.000 | 5.400.000 |
| Resto de componentes | ~3.595.000 | ~900.000 | ~27.000.000 |
| **Total** | **~8.417.900** | **~2.420.000** | **~72.600.000** |

## Aclaraciones

- **Precios volátiles:** en Argentina los precios de hardware varían fuerte por tipo de cambio, impuestos y promociones. Los valores son de referencia (junio 2026) y deben confirmarse antes de comprar.
- **Crisis de la RAM:** como explicamos arriba, el precio de la DDR5 está en un momento histórico de subas (algunos análisis hablan de subas acumuladas de entre 300% y 400% desde mediados de 2025), así que conviene chequear el precio actualizado el día de la compra, puede haber cambiado bastante incluso entre que entregamos este trabajo y la fecha de la defensa.
- **Medios de pago:** los precios relevados suelen corresponder a pago con débito/transferencia/efectivo; en cuotas o con tarjeta de crédito el precio final sube.
- **Ítems marcados como "estimado":** cuando no encontramos el modelo exacto publicado con precio en una tienda argentina, estimamos el valor a partir de productos de la misma gama/categoría que sí encontramos. Antes de una compra real, habría que cotizar el modelo puntual.
- **Disponibilidad:** algunos productos pueden figurar momentáneamente sin stock; en ese caso se reemplazan por equivalentes de la misma gama.