# Ficha técnica de la base de datos
## Características generales
- Tipo de datos: biodiversidad, conservación y atención digital de especies.
- Unidad de análisis: especies amenazadas del reino Animalia presentes en Chile.
- Cobertura territorial: Chile.
- Categorías consideradas: CR y EN.
- Fuente principal de visitas: Wikipedia Pageviews Analysis.
- Formato original de la base: Excel.
- Formato procesado para visualización: CSV.
- Total de especies consideradas en la base: 216.
- Total de especies visualizadas: 23.

## Variables incorporadas
| Variable                           | Descripción                                                |
| ---------------------------------- | ---------------------------------------------------------- |
| ID                                 | Número identificador de la especie                         |
| Nombre Científico                  | Nombre científico registrado para la especie               |
| Nombre Común                       | Nombre común asociado a la especie                         |
| Clase                              | Clase taxonómica de la especie                             |
| RCE                                | Categoría de conservación de la especie                    |
| Total Visitas (periodo seis meses) | Total acumulado de visitas en Wikipedia durante seis meses |
| Promedio Diario                    | Promedio diario de visitas registrado                      |
| URL Fuente                         | URL utilizada para obtener los datos de visitas            |

## Observaciones sobre la base de datos
- La base considera únicamente especies pertenecientes al reino Animalia.
- La base incluye especies clasificadas en categorías CR y EN.
- Las visitas corresponden exclusivamente a páginas de Wikipedia en inglés.
- Algunas especies no poseen nombre común registrado.
- La visualización trabaja con una selección específica de especies correspondientes al top 10, bottom 10 y especies mediáticas.
- Algunas especies consideradas “mediáticas” fueron incorporadas para efectos comparativos dentro de la visualización.
- La base de datos original considera 216 especies registradas. Sin embargo, la visualización final utiliza una selección reducida de especies para facilitar la comparación de atención digital entre casos altamente visibles y especies prácticamente invisibles.