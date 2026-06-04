# Visualización especies más y menos buscadas
## Descripción del proyecto
Esta visualización busca representar la desigualdad de atención digital que reciben distintas especies amenazadas en Chile a través de sus visitas en Wikipedia. Utilizando un gráfico de puntos horizontal desarrollado con la librería Altair de Python, se comparan las especies más visitadas y menos visitadas dentro de la base de datos elaborada para el proyecto, incorporando además algunas especies consideradas “mediáticas”.

La visualización fue diseñada para complementar una crónica periodística sobre biodiversidad y conservación, permitiendo observar cómo ciertas especies logran instalarse dentro del imaginario colectivo mientras otras permanecen prácticamente invisibles para el público general.

## Proceso de visualización
La visualización fue desarrollada en Google Colab utilizando Python y la librería Altair.

### Pasos realizados
- Se cargó la base de datos en formato CSV utilizando pandas.
- Se revisaron las columnas disponibles y se identificaron las variables relevantes para el análisis.
- Se transformó la columna de visitas totales a formato numérico.
- Se eliminaron filas con datos faltantes.
- Los datos fueron ordenados según la cantidad total de visitas registradas en Wikipedia.
- Se seleccionaron las 10 especies más visitadas y las 10 menos visitadas de la base de datos.
- Se incorporaron tres especies consideradas mediáticas dentro del análisis:

    1. Hippocamelus bisulcus
    2. Rhinoderma darwinii
    3. Spheniscus humboldti

- Se creó una etiqueta combinando nombre científico y nombre común para mejorar la lectura de la visualización.
- Finalmente, se diseñó un gráfico de puntos horizontal utilizando Altair.
- La visualización fue exportada en formato HTML y JPG.

### Decisiones tomadas
Inicialmente se consideró utilizar un gráfico de dispersión, pero esta opción dificultaba la lectura debido a la cantidad de especies presentes en la base de datos.

Por esta razón, se decidió utilizar un gráfico de puntos horizontal, ya que:
- Facilita la comparación entre especies.
- Permite visualizar claramente las diferencias de atención digital.
- Funciona mejor con nombres científicos largos.
- Es una visualización clara y adecuada para formato webstory.

Además, se decidió comparar únicamente las especies más visitadas y menos visitadas para enfatizar visualmente la desigualdad de atención pública.

También se incorporó una categoría diferenciada para las especies mediáticas utilizando un color distinto, permitiendo compararlas con especies poco conocidas o invisibles digitalmente.

### Base de datos utilizada
La base de datos utilizada corresponde a especies amenazadas presentes en Chile y sus visitas acumuladas en Wikipedia durante un período de seis meses.

La información fue organizada inicialmente en formato Excel y posteriormente exportada a CSV para facilitar su procesamiento en Python.

### Procesamiento de la base de datos
Para preparar la base:

- Se verificaron manualmente las visitas acumuladas de cada especie utilizando Wikipedia Pageviews Analysis.
- Se calcularon los promedios diarios de visitas.
- Se corrigieron registros incompletos o inconsistentes.
- Se eliminaron filas inválidas para la visualización.
- Se ordenaron las especies según su cantidad de visitas.
- Se seleccionaron las especies necesarias para la comparación visual.

La base fue seleccionada porque permite observar diferencias de atención digital entre especies amenazadas y relacionarlas con su nivel de reconocimiento público.

## Preguntas que puede responder la visualización
1. ¿Qué especies amenazadas reciben mayor atención digital?
2. ¿Qué especies registran menos visitas en Wikipedia?
3. ¿Qué diferencias existen entre especies mediáticas y especies poco conocidas?