# README — Visualización de especies amenazadas por región

## Descripción del proyecto

Esta visualización busca representar la distribución regional de especies clasificadas en categorías de amenaza en Chile, específicamente aquellas catalogadas como “En Peligro Crítico” (CR), “En Peligro” (EN) y “EN-RARA”. A través de un gráfico de barras horizontales apiladas desarrollado con la librería Altair de Python, se comparan las regiones del país según la cantidad de especies presentes en cada categoría.

La visualización fue diseñada para complementar una crónica periodística sobre biodiversidad y especies amenazadas, permitiendo identificar territorialmente dónde se concentran mayores niveles de riesgo para la fauna y flora.


## Proceso de visualización

La visualización fue desarrollada en Google Colab utilizando Python y la librería Altair.

## Pasos realizados

1. Se cargó la base de datos original en formato Excel (.xlsm) utilizando pandas.

2. Se revisaron las columnas disponibles y se identificaron las variables relevantes para el análisis.

3. Se filtraron únicamente las especies clasificadas en las categorías:

   - CR (En Peligro Crítico)

   - EN (En Peligro)

   - EN-RARA (En Peligro-Rara)

4. Los datos fueron agrupados por región y categoría de conservación.

5. Se contabilizó la cantidad de especies por cada región.

6. Se diseñó una visualización de barras horizontales apiladas utilizando Altair.

7. Se incorporó un sistema de tooltip interactivo para visualizar información específica al pasar el cursor sobre cada barra.

8. Se añadió un resumen superior con el total de especies por categoría y el total general.

9. Finalmente, la visualización fue exportada en formato HTML y JPG.


## Decisiones tomadas

Decidí utilizar un gráfico de barras horizontales apiladas debido a que:

- Facilita la comparación entre regiones.

- Permite visualizar simultáneamente las categorías CR, EN y EN-RARA.

- Los nombres de las regiones son extensos y se leen mejor horizontalmente.

- Es una visualización clara y adecuada para formato webstory.

Además, se utilizaron colores diferenciados para cada categoría:

- Verde para especies CR.

- Morado para especies EN.

- Celeste para especies EN-RARA.

Esto permite distinguir visualmente los distintos niveles y categorías de amenaza.


## Base de datos utilizada

La base de datos utilizada corresponde a registros de especies clasificadas según categoría de conservación y región de distribución.

La base fue trabajada inicialmente en formato Excel (.xlsm) y posteriormente procesada en Python.

## Procesamiento de la base de datos

Para preparar la base:

- Se filtraron únicamente las categorías CR, EN y EN-RARA.

- Se eliminaron registros no necesarios para la visualización.

- Se agruparon los datos por región y categoría.

- Se contabilizó el número total de especies por combinación de variables.

La base fue seleccionada porque permite observar territorialmente la distribución de especies amenazadas y relacionarla con problemáticas ambientales regionales.

## Correcciones y verificación de la base de datos

Previo a la elaboración de la visualización se realizó una revisión y corrección de la base de datos original, enfocada principalmente en verificar la condición de endemismo de las especies registradas.

A partir de esta revisión se detectaron inconsistencias en la clasificación original:

- 9 especies figuraban como no endémicas, pese a que sí correspondían a especies endémicas de Chile.
- 2 especies (_Basilichthys semotilus_ y _Liolaemus thermarum_) aparecían registradas erróneamente como endémicas.

Debido a estas correcciones, la cantidad total de especies consideradas pasó de 206 registros en la base original a 214 especies en la versión final procesada para la visualización.

Estas modificaciones permitieron trabajar con una base de datos más precisa y consistente para el análisis territorial de especies amenazadas en Chile.

## Preguntas que puede responder la visualización

La visualización permite responder preguntas como:

- ¿Qué regiones concentran mayor cantidad de especies amenazadas?

- ¿Dónde existen más especies en peligro crítico?

- ¿Cómo se distribuyen territorialmente las categorías CR, EN y EN-RARA?

- ¿Qué regiones presentan mayores niveles de vulnerabilidad ecológica?
