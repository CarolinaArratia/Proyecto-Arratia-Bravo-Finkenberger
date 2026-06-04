
## 1. Proceso de Visualización: Pasos y Decisiones

La visualización fue desarrollada utilizando la librería **Altair** en un entorno de **Google Colab**. El objetivo principal fue transformar datos estadísticos en una narrativa visual que denunciara la **asfixia del espacio mediático**.

### Pasos técnicos:
1.  **Modelado de Mosaico:** Se optó por un gráfico de rectángulos proporcionales para representar el "espacio" de prensa como un recurso finito. Se calcularon coordenadas acumuladas (`x0` y `x1`) para que el ancho de cada bloque correspondiera exactamente al porcentaje de apariciones de la especie.
2.  **Jerarquía Visual y Legibilidad:** Debido a la compresión del espacio, los nombres de las especies tendían a superponerse. Se aplicó una **rotación de 270 grados** a las etiquetas, permitiendo que las palabras se lean verticalmente, aprovechando la altura del bloque.
3.  **Configuración del Lienzo:** Se ajustó la altura de los bloques a **350 píxeles** y el lienzo general a **400 píxeles**, encontrando el equilibrio perfecto para una visualización que debe integrarse en un formato de *webstory*.
4.  **Interactividad:** Se implementó una **ficha técnica interactiva** (tooltip) que se activa al pasar el cursor, permitiendo que las especies con menor presencia informativa sigan entregando sus datos técnicos al lector.

### Decisiones de Diseño:
* **Color Editorial:** Se utilizaron tonos **púrpura y fucsia** para los títulos y subtítulos para mantener la identidad visual del reportaje.
* **Color de Datos:** Se asignó **Naranja (#F57C00)** para especies en Peligro Crítico (CR) y **Verde (#4CAF50)** para especies En Peligro (EN).

## 2. Base de Datos (CSV) y Procesamiento

### Selección y Filtrado de la Base:
El proceso comenzó con una base de datos exhaustiva del **Reglamento de Clasificación de Especies (RCE)** que contenía **más de 200 especies amenazadas** registradas en Chile. Sin embargo, para efectos de esta investigación periodística, se aplicó un **filtro de relevancia mediática**.

La base de datos definitiva, denominada `06_Recuento_noticias.csv`, es el resultado de contrastar ese listado masivo contra un monitoreo de prensa nacional de los **últimos seis meses**. Se descartaron todas aquellas especies que no registraron ninguna mención, dejando únicamente a las especies que **efectivamente aparecieron en las noticias**. Este criterio de selección es fundamental para la hipótesis del trabajo: no se busca mostrar cuántas especies existen, sino **quiénes logran existir dentro del relato público**. Además, para esta visualización se optó por incluir solamente las especies CR del registro original del MMA y compararlas con 3 especies que son conocidamente más mediáticas.

### Procesamiento de los Datos:
1.  **Limpieza de Registros:** Se estandarizaron los nombres científicos y comunes tras el filtrado para asegurar la integridad de la visualización.
2.  **Cálculo de Proporciones:** Se creó la variable `prop` (proporción), dividiendo las apariciones individuales por el total de la muestra (noticias totales) para generar la geometría del mosaico.
3.  **Regla de Etiquetado:** Se aplicó un filtro lógico para que solo las especies con 4 o más apariciones (hasta el Caracol de Paposo) imprimieran su nombre, evitando el caos visual y reforzando gráficamente la tesis de que las demás son "invisibles".

## 3. Preguntas que responde la visualización

La visualización final actúa como una herramienta de auditoría mediática, respondiendo preguntas como:

* **¿Existe acaparamiento informativo?** Sí, el gráfico revela que especies como el Pingüino de Humboldt ocupan más del 50% de la conversación total.
* **¿Qué tan invisibles son las especies en Peligro Crítico?** Permite identificar especies en categoría CR que, a pesar de su riesgo inminente, poseen bloques representados por líneas delgadas de una sola mención.
* **¿Cuál es la brecha de protagonismo?** Responde cuántas especies son mencionadas pero no logran ser el eje central de la noticia (ej. Ranita de Darwin del Norte).
* **¿Cómo influye la categoría de riesgo en la cobertura?** Permite observar si el nivel de urgencia biológica (CR vs EN) se traduce en una mayor o menor cuota de pantalla.