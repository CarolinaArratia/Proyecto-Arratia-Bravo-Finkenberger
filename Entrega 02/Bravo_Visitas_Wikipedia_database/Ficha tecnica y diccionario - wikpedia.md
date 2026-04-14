## 3.1. Ficha Técnica: Índice de Curiosidad Digital

### **Fuente de los datos:**
Los datos provienen de la herramienta Pageviews Analysis de la Fundación Wikimedia. La recolección se realizó utilizando la versión en inglés de Wikipedia (en.wikipedia.org) para medir el impacto de las especies chilenas en una plataforma de alcance global.

### **Metodología de la construcción de la base:**
La base de datos se construyó mediante la identificación de 70 especies presentes en el territorio nacional. Se realizó una búsqueda individual para cada una en el portal de estadísticas de Wikipedia, configurando el filtro para excluir visitas de "agentes" (bots) y capturar solo el interés de usuarios reales. Para aquellas especies que no cuentan con un artículo propio o que no registraron actividad, se dejó constancia explícita en la tabla.

### **Alcance de los datos:**
El periodo de análisis comprende exactamente seis meses, desde el 25 de septiembre de 2025 hasta el 25 de marzo de 2026. La base abarca una muestra de biodiversidad compuesta por 70 registros que incluyen diversos grupos taxonómicos como anfibios, aves, reptiles, insectos, arácnidos y crustáceos.

### **Características de los datos:**
Se trata de una base de datos tabular que combina variables cualitativas (nombres científicos y clasificación taxonómica) con métricas cuantitativas de tráfico web. Los datos permiten observar la disparidad de interés entre distintas especies; por ejemplo, el Sapo de Danko (Telmatobius dankoi) lidera las visitas con un total de 686, mientras que especies como la Pancora (Aegla denticulata) carecen de sitio web registrado.

### **Otras observaciones:**
Un hallazgo relevante en la base es el alto número de especies (como el caracol Ambrosiella kuscheli o el seudoescorpión Anaperochernes ambrosianus) que figuran "Sin datos" o "Sin sitio web". Esto refuerza el argumento de la investigación sobre la invisibilidad digital de gran parte de la fauna chilena en peligro.

## 3.2. Diccionario de datos

| Nombre de la Variable | Descripción | Tipo de Dato | Valores Posibles | Observaciones Editoriales |
| :--- | :--- | :--- | :--- | :--- |
| **ID** | Identificador numérico único asignado a cada especie para facilitar la organización y el cruce de datos. | Numérico (Entero) | 1 al 70. | Clave primaria de la base de datos. |
| **Nombre Científico** | Denominación técnica en latín de la especie según la taxonomía oficial. | Texto | Ejemplo: *Alsodes laevis*. | Variable principal de identificación para la validación de datos. |
| **Nombre Común** | Nombre popular o descriptivo con el que se reconoce a la especie en Chile. | Texto | Ejemplo: Sapo de Danko. | Incluye términos genéricos cuando no existe una denominación específica. |
| **Clase** | Categoría taxonómica superior que permite agrupar a las especies por tipo biológico. | Texto | Amphibia, Aves, Insecta, etc. | Crucial para el análisis de sesgos de interés por grupo taxonómico. |
| **Total Visitas (periodo seis meses)** | Sumatoria de visualizaciones humanas registradas entre el 25/09/25 y el 25/03/26. | Numérico / Texto | 0 a 686 / "Sin sitio web" / "Sin datos". | Indica la magnitud total de la curiosidad digital acumulada. |
| **Promedio Diario** | Frecuencia media de visitas que recibe el artículo de la especie cada día. | Numérico / Texto | 0 a 4 / "Sin sitio web" / "Sin datos". | Permite normalizar el impacto diario independientemente del volumen total. |
| **URL Fuente** | Enlace directo a las estadísticas de Pageviews Analysis de Wikipedia. | Texto (URL) | Enlaces de wmcloud.org. | Solo disponible para especies con rastro digital en la plataforma. |