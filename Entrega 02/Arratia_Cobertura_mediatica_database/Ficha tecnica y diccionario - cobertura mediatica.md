# Ficha técnica y diccionario

### Fuente de los datos:

**Nómina oficial de especies:** Elaboración propia a partir de la base de datos bruta del Reglamento de Clasificación de Especies (RCE) del Ministerio del Medio Ambiente. Se realizó un proceso de filtrado y selección para reducir el universo de datos a una muestra representativa de 70 especies.

**Registro de prensa:** Captura de noticias en tiempo real a través de SerpApi, utilizando el motor de búsqueda de Google News para obtener resultados de medios digitales chilenos.

### Metodología de la construcción de la base:
La base se construyó bajo un modelo de doble verificación. Para cada una de las 70 especies, se configuraron dos cadenas de búsqueda independientes: una para el nombre común y otra para el nombre científico. Esta decisión se tomó para identificar la brecha entre el lenguaje técnico de los especialistas y el lenguaje cotidiano de la prensa generalista. Los resultados fueron procesados individualmente para descartar falsos positivos y asegurar que cada mención se refiriera efectivamente al ejemplar biológico.

### Alcance de los datos

**Temporal:** Noticias publicadas entre el 01 de septiembre de 2025 y el 10 de abril de 2026.

**Geográfico:** Medios digitales con dominio en Chile (.cl) o con secciones específicas de noticias nacionales, abarcando desde grandes diarios santiaguinos hasta boletines regionales y radios locales.

### Característica de los datos:
La base principal es un archivo maestro donde cada fila representa una especie única vinculada a un ID numérico. Este ID es el eje que conecta los datos de prensa con los registros de respaldo guardados en formato CSV.

| Nombre de Variable | Qué significa | Tipo de dato | Valores |
| :--- | :--- | :--- | :--- |
| **Especie ID** | Código único de identificación. | Número | 1 al 70 |
| **Nombre científico** | Denominación en latín de la especie. | Texto | *Nombre en latín* |
| **Nombre común** | Nombre popular en Chile. | Texto | *Nombre común* |
| **Clase** | Categoría biológica superior de la especie. | Texto | Gastropoda, Malacostraca, Amphibia, etc. |
| **Usa N. Científico** | Si la noticia usa el nombre técnico. | Número | 0 (No) / 1 (Sí) |
| **Usa N. Común** | Si la noticia usa el nombre popular. | Número | 0 (No) / 1 (Sí) |
| **Mención nacional** | Conteo de apariciones en medios grandes. | Número | 0, 1, 2... |
| **Mención regional** | Conteo en diarios locales o regionales. | Número | 0, 1, 2... |
| **Tiene foto** | Si la noticia muestra visualmente al animal. | Número | 0 (No) / 1 (Sí) |
| **Tono** | El enfoque o sentimiento principal de la noticia. | Texto | Informativo, Alarmista, Político, Denuncia. |

## Otras observaciones ##
Se dio prioridad a la calidad sobre la cantidad. En casos donde una búsqueda arrojaba cientos de resultados por confusión de nombres (homonimia), se aplicaron filtros manuales rigurosos en lugar de dejar que el algoritmo decidiera, para evitar que la base de datos se ensuciara con información irrelevante.