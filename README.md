# Andes Retail Group — Dashboard de Desempeño Comercial 2024-2025

Dashboard en Power BI para el análisis del desempeño comercial de una empresa retail ficticia (proyecto capstone del bootcamp de Análisis de Datos, TripleTen), con operaciones en Perú, Chile y Colombia.

**Dataset:** 5,000 pedidos completos (2024-2025) | 4 categorías de producto (Electrónica, Ropa, Deportes, Hogar) | 3 segmentos de cliente (Premium, Estándar, Económico)

---

## Contexto y objetivo

El dashboard responde seis preguntas de negocio centrales sobre evolución de ingresos, rentabilidad, comportamiento por segmento/categoría, diferencias geográficas y patrones estacionales organizadas en dos vistas con propósitos distintos:

- **Overview:** ¿Cómo evolucionó el ingreso entre 2024 y 2025?
- **Detalle:** ¿Por qué subieron, bajaron o se mantuvieron los ingresos?

Cada vista sigue el framework narrativo **SCQA** (Situación → Complicación → Pregunta → Respuesta) para conectar los hallazgos con una historia coherente, en lugar de presentar gráficos sueltos.

---

## Vista Overview

**KPIs:** Ingresos totales ($5.53M), Rentabilidad (35.10%), Pedidos totales (5,000), Ticket promedio ($1,106)

**Visuales:** línea comparativa mensual (2024 vs 2025), ingresos por categoría, país y segmento de cliente.

**Filtro:** Año

### SCQA — Overview

**S (Situación):** Los ingresos totales entre 2024 y 2025 alcanzaron $5.53 millones, con un comportamiento desigual entre ambos años: 2024 tuvo mayor fuerza en el arranque (enero-marzo) y en el cierre (diciembre), mientras que 2025 se mantuvo por debajo en esos mismos periodos.

**C (Complicación):** El patrón no es uniforme a lo largo del año: 2025 arranca por debajo de 2024 en el bimestre enero-febrero (-15% y -16% respectivamente) y vuelve a quedar por debajo en el cierre de diciembre (-18%). En los meses intermedios (marzo a noviembre) las diferencias no siguen una dirección consistente — hay caídas puntuales (mayo -10%, julio -13%) y meses donde 2025 supera a 2024 (octubre +13%), pero ninguno alcanza la magnitud ni la persistencia del bloque enero-febrero-diciembre.

**Q (Pregunta):** ¿A qué se asocia que 2025 no alcance los niveles de 2024 específicamente en ese bloque de enero-febrero-diciembre?

**A (Respuesta):** El Overview no tiene el desglose necesario para responder esto — ese bloque de meses corresponde a la temporada de Verano, y se retoma en la vista Detalle con el desglose por segmento y país.

---

## Vista Detalle

**Visuales:**
- Ingresos por temporada (Año como leyenda) — expone la caída concentrada en Verano.
- Ingresos por segmento de cliente en Verano (Año como leyenda) — aísla el driver del hallazgo anterior.
- Participación de nivel de venta (Alta/Baja) por segmento de cliente — hallazgo estructural, no estacional.
- Línea de ingresos mensuales, filtrable por país — expone la divergencia de Colombia.
- Tabla País × Segmento_Cliente (pedidos, ingresos, ticket promedio) — evidencia numérica exacta.

**Filtros:** Año, País

### SCQA — Detalle

**S (Situación):** En 2025, los ingresos por temporada muestran una caída concentrada en Verano (-16.6% vs 2024), mientras Otoño, Invierno y Primavera se mantienen estables o crecen.

**C (Complicación):** Este patrón no es uniforme entre países: Colombia se comporta de forma distinta, con incrementos de 50% en febrero y 27% en septiembre de 2025 frente a 2024, justo cuando el resto del mercado muestra debilidad o estabilidad.

**Q (Pregunta):** ¿A qué se asocia la caída generalizada de Verano, y por qué Colombia no sigue ese mismo patrón?

**A (Respuesta):** La caída de Verano se concentra en el segmento Premium, que registra 58 pedidos menos que en 2024 (-26%) y explica la mayor parte de la contracción (-27.7% en ingresos), mientras Estándar y Económico se mantienen relativamente estables. A nivel país, Chile y Perú siguen este patrón, pero Colombia no — no porque esté exenta de la debilidad de enero (de hecho la sufre con más fuerza, -37.5%), sino porque un repunte de febrero (+49.9%) compensa casi por completo esa caída, dejando su Verano neto casi plano.

---

## Hallazgos adicionales

- **Estándar concentra el mayor volumen de pedidos (2,504) pero el 59% son transacciones de bajo valor** — la oportunidad comercial más accionable no está en un país ni una temporada, está en cómo se convierte al cliente Estándar hacia compras de mayor valor. Este patrón es transversal a los 3 países, no explica ni la caída de Verano ni la divergencia de Colombia (son fenómenos independientes, verificados por separado).
- **Margen de rentabilidad (34.9%-35.3%) y distribución por región resultaron ser no-diferenciadores** — descartados explícitamente tras verificar que no aportan variación explicativa, evitando forzar conclusiones donde solo hay ruido.
- **La caída de Colombia y de Premium en Verano son problemas de volumen de pedidos, no de ticket promedio** — un hallazgo consistente en ambos cortes del análisis.

---

## Herramientas

Power BI Desktop · DAX · Excel (preparación de datos)
