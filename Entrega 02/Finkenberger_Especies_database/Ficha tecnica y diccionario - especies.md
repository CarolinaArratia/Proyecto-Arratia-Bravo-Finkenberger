# 3. Ficha técnica y diccionario de datos 

- Fuente de los datos:

La base de datos utilizada proviene del Ministerio del Medio Ambiente de Chile, específicamente de los registros oficiales del Reglamento de Clasificación de Especies (RCE), los cuales contienen información sobre el estado de conservación de la biodiversidad en el país.

- Metodología de la construcción de la base:

Se construyeron múltiples bases de datos a partir de una nómina original sin limpiar. En una primera etapa, se seleccionaron variables relevantes y se filtraron especies del reino Animalia, endémicas de Chile y en categoría de peligro crítico (CR). Posteriormente, estas fueron organizadas por región, replicando registros según su distribución territorial. Este procedimiento se replicó para especies en categoría “en peligro” (EN) y, finalmente, se generó una base consolidada que integra ambas categorías.

- Alcance de los datos:

La base incluye especies animales endémicas de Chile clasificadas en las categorías de peligro crítico de extinción (CR) y en peligro (EN), junto con su distribución regional. Se excluyen especies de otros reinos, aquellas que no son endémicas y las que pertenecen a otras categorías de conservación.

Asimismo, la base no incorpora información sobre la cantidad de individuos por especie, ya que este dato no se encuentra disponible en la fuente original. Tampoco incluye tablas de carácter estadístico o de resumen, como aquellas que agrupan el número de especies por categoría.

- Características de los datos:

La base corresponde a datos estructurados, organizados en formato tabular. Predominan los datos de tipo cualitativo y categórico, tales como nombre de la especie, clasificación biológica, categoría de conservación y distribución geográfica. 

- Otras observaciones:

Se mantuvieron categorías específicas como “ENR” para conservar información relevante. Asimismo, se conservaron registros con ausencia de datos (“sin datos”) para evitar la pérdida de información en la tabla reducida; sin embargo, estos no se consideraron en la distribución de presencia por región, debido justamente a la falta de información disponible.

## Diccionario de datos

| Nombre_variable    | Etiqueta                                              | Tipo        | Valores posibles                              |
|-------------------|-------------------------------------------------------|-------------|----------------------------------------------|
| nombre_científico | Nombre científico de la especie                       | texto       | Texto libre                                 |
| nombre_común      | Nombre común de la especie                            | texto       | Texto libre                                 |
| reino             | Reino biológico al que pertenece la especie           | categórico  | Animalia                                    |
| clase             | Clase biológica de la especie                         | categórico  | Mamífero, Ave, Reptil, Anfibio, etc.        |
| endémico_chile    | Indica si la especie es endémica de Chile             | categórico  | Sí                                          |
| categoria         | Categoría de conservación de la especie               | categórico  | CR, EN, ENR                                 |
| región            | Región del territorio chileno donde habita la especie | texto       | Regiones de Chile                           |
| presencia_region  | Registro de presencia de la especie en una región     | numérico    | 1 (Una fila representa una presencia)       |

**Nota:** 
En las bases de datos organizadas por región, una misma especie puede aparecer en múltiples filas, ya que se registra una vez por cada región en la que está presente. Esto permite analizar la distribución territorial de las especies.


				
				
				
				
				
				
				