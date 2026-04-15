# Ficha técnica y diccionario

### Fuente de los datos:

**Nómina oficial de especies:** Elaboración propia a partir de la base de datos bruta del Reglamento de Clasificación de Especies (RCE) del Ministerio del Medio Ambiente. Se trabajó con un universo de 70 especies seleccionadas por su estado de conservación (Peligro Crítico y En Peligro).

**Registro de prensa:** Captura de noticias en tiempo real a través de SerpApi (Google News), filtrando resultados de medios digitales chilenos publicados entre octubre de 2025 y abril de 2026.

### Metodología de la construcción de la base:
La base se construyó bajo un modelo de **Formato Largo (Long Format)**. Esto significa que si una especie aparece en tres noticias distintas, tiene tres filas en la base de datos. Si una noticia menciona a dos especies de la lista, se crearon dos filas independientes con la misma URL pero distinto ID de especie.

Se aplicó un filtro de **Rigor Taxonómico**: solo se contabilizaron noticias donde el nombre científico o el nombre común coincidieran exactamente con el sujeto de estudio. Este proceso permitió identificar descalces científicos en la prensa, donde se usan nombres comunes para especies que no corresponden a la ficha técnica oficial.

### Alcance de los datos

**Temporal:** Noticias publicadas entre el 13 de octubre de 2025 y el 13 de abril de 2026.

**Geográfico:** Medios digitales chilenos (.cl), segmentados en **Nacional** (medios con base en Santiago y alcance país como BioBioChile o El Mostrador) y **Regional** (medios locales como El Morrocotudo).

### Característica de los datos:
La base final consta de **21 filas de análisis** derivadas de **14 noticias únicas**. Es una base de datos procesable donde las variables cualitativas fueron transformadas a formato binario (1 y 0) para permitir cálculos de porcentajes y visualizaciones.

### Diccionario de datos

La base de datos se organiza en una tabla única vinculada a un ID numérico. Este ID es el eje que conecta los datos de prensa con los registros de respaldo del Ministerio.

| Nombre de Variable | Qué significa | Tipo de dato | Valores |
| :--- | :--- | :--- | :--- |
| **Especie ID** | Código único de identificación (RCE). | Número | 1 al 70 |
| **Nombre científico** | Denominación en latín de la especie. | Texto | *Binomio en latín* |
| **Nombre común** | Nombre popular reconocido en la lista. | Texto | *Nombre común* |
| **ID Noticia** | Titular del artículo analizado. | Texto | Título de la noticia |
| **URL** | Link directo a la fuente de información. | Texto/URL | Link |
| **Fuente** | Nombre del medio de comunicación. | Texto | BioBioChile, Ladera Sur, etc. |
| **Usa N. Científico** | Si la noticia menciona el nombre técnico correcto. | Número | 0 (No) / 1 (Sí) |
| **Usa N. Común** | Si la noticia usa el nombre popular. | Número | 0 (No) / 1 (Sí) |
| **Alcance** | Cobertura geográfica del medio. | Texto | Nacional / Regional |
| **Es protagonista** | Si la especie es el centro de la noticia. | Número | 0 (No) / 1 (Sí) |
| **Tiene foto** | Si hay apoyo visual de la especie. | Número | 0 (No) / 1 (Sí) |
| **Tono predominante** | El enfoque editorial de la noticia. | Texto | Alerta, Positivo, Crítico, Científico |

## Otras observaciones
Se aplicó un criterio de exclusión estricto: noticias sobre "arrecifes de coral" o "pingüinos de Humboldt" fueron ignoradas al no formar parte de la muestra asignada (IDs 1-70), asegurando la limpieza estadística de la investigación grupal.

Para esta entrega solo se consideró una muestra de 70 especies en Peligro Crítico, que luego se ampliará a 206 especies (Peligro Crítico y En Peligro) para un análisis mas completo.