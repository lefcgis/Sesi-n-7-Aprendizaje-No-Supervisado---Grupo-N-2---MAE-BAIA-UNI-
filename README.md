## **Validación Matemática vs. Decisión Operativa en Consultoría Ambiental**

# MAE BAIA UNI - Documento de discusión interna · Mayo 2026  
**Grupo 2**
- Joel Apolaya
- Eduardo Cabrera
- Luis Ferrer 
- Francisco Vela


---

## Dolor

Un equipo de línea base física presenta la zonificación ambiental de un proyecto MEIA con **5 unidades ambientales**, porque "así lo hemos manejado históricamente en proyectos similares". Se implementa un análisis de clustering (K-Means) sobre los datos fisicoquímicos de 40 estaciones de monitoreo de agua, y los resultados arrojan que el **Silhouette Score es 0.42 con K=5** y **0.61 con K=3**.

Los datos sugieren que 3 zonas describen mejor la realidad ambiental del área de estudio. El equipo técnico insiste en 5.

¿Qué hacemos? ¿La métrica manda, o el criterio del especialista prevalece?

---

## Qué nos dice cada número

El Silhouette Score mide qué tan bien "encajan" los datos dentro de su grupo asignado comparado con los grupos vecinos. Su rango va de -1 a 1.

| Score | Interpretación práctica |
|-------|------------------------|
| 0.71 – 1.00 | Estructura fuerte: los grupos están bien separados |
| 0.51 – 0.70 | Estructura razonable: los grupos son distinguibles |
| 0.26 – 0.50 | Estructura débil: los grupos se superponen |
| ≤ 0.25 | Sin estructura significativa |

Con K=5, el score de 0.42 nos dice que forzar 5 zonas genera grupos que se traslapan. Hay estaciones que no pertenecen claramente a ninguna de las 5 zonas. Con K=3, el score de 0.61 indica que los datos se organizan de forma más nítida en 3 agrupaciones, con menos ambigüedad.

En términos ambientales: los datos de campo sugieren que el territorio estudiado tiene **3 condiciones ambientales diferenciables**, no 5. Cuando el especialista define 5, posiblemente está subdividiendo zonas que en la práctica presentan **condiciones similares**.

---

## Por qué la respuesta no es simplemente "gana K=3"

La validación matemática **no siempre tiene prioridad sobre la decisión operativa**, y en el contexto de LA COMPAÑÍA hay razones concretas para ello.

**SENACE y la normativa peruana no evalúan Silhouette Scores.** El revisor del instrumento de gestión ambiental evalúa si la zonificación es coherente con la descripción del medio físico y si los impactos están adecuadamente identificados para cada zona. Si históricamente los proyectos del mismo sector han trabajado con 5 unidades y SENACE las ha aprobado, hay un **precedente regulatorio que tiene peso**.

**El especialista integra información que el algoritmo no ve.** El clustering trabaja solo con la matriz numérica de parámetros fisicoquímicos. El especialista de LBF, en cambio, integra la geomorfología, el régimen hidrológico, la estacionalidad, el uso actual del suelo y su conocimiento de campo. Puede haber razones técnicas legítimas para separar dos zonas que estadísticamente son similares en calidad de agua, **pero que difieren en riesgo geológico o en presión antrópica**.

**El Downstream Impact importa.** Cada unidad ambiental genera **obligaciones** en el Plan de Manejo: programas de monitoreo diferenciados, medidas de mitigación específicas, compromisos de reporte. Reducir de 5 a 3 zonas puede **simplificar el estudio**, pero también puede generar la observación de que se está **subestimando la heterogeneidad ambiental** del área — un riesgo que el equipo técnico conoce bien.

---

## Cómo se negocia esta decisión en LA COMPAÑÍA

La negociación no es "dato vs. opinión", sino convergencia informada. El enfoque recomendado tiene tres pasos.

**Paso 1 — Presentar, no imponer.** GSI presenta al equipo técnico los resultados del clustering como **evidencia complementaria**, no como veredicto. Se muestra la curva del método del codo, los Silhouette Scores para K=2 hasta K=8, y el dendrograma jerárquico. El objetivo es que el especialista vea los **patrones**, no que acepte un número.

**Paso 2 — Explorar el rango intermedio.** Si K=3 es matemáticamente óptimo y K=5 es la preferencia operativa, ¿qué pasa con K=4? ¿El score baja mucho? ¿Las dos zonas adicionales tienen justificación ambiental? A veces la solución está en un punto intermedio donde ambas miradas convergen.

**Paso 3 — Documentar la decisión.** Si el equipo decide mantener K=5 con argumentos técnicos válidos (regulatorios, de conocimiento de campo, de gestión de impactos), se documenta la justificación. Si decide ajustar a K=3 o K=4, también. Lo importante es que la decisión ya no es "porque siempre lo hicimos así", sino una elección informada con evidencia cuantitativa sobre la mesa.

---

## El valor real para LA COMPAÑÍA

La pregunta de fondo no es si la matemática manda o no. Es si LA COMPAÑÍA quiere tomar decisiones técnicas basadas en evidencia cuantitativa o solo en experiencia acumulada. La respuesta, naturalmente, es en ambas.

El clustering no llega a reemplazar al especialista. Llega a darle una herramienta que hoy no tiene: una **validación independiente de su criterio experto**, basada en los mismos datos que él levantó en campo. Cuando el algoritmo coincide con el especialista, refuerza la **confianza** en la zonificación ante SENACE. Cuando no coincide, abre una **conversación técnica valiosa** que puede mejorar el producto final.

Para la línea de innovación de GSI, esta capacidad representa un diferenciador competitivo frente a consultoras que siguen zonificando exclusivamente por criterio experto. No porque el criterio experto sea malo — es indispensable — sino porque complementarlo con análisis cuantitativo **eleva el estándar técnico y reduce la subjetividad ante el regulador**.

---

## Conclusión operativa

La validación matemática no siempre tiene prioridad sobre la decisión organizacional. Pero la decisión organizacional que ignora la evidencia matemática disponible es una decisión **más débil** que la que la incorpora y decide con conocimiento de causa.

En LA COMPAÑÍA, la propuesta de GSI no es que el Silhouette Score defina cuántas unidades ambientales tiene un EIA. Es que el equipo técnico tenga ese dato sobre la mesa **antes de decidir**.

---

*Referencia metodológica: Hastie, T., Tibshirani, R. y Friedman, J. (2009). The Elements of Statistical Learning (2.ª ed.). Springer, Cap. 14.*
