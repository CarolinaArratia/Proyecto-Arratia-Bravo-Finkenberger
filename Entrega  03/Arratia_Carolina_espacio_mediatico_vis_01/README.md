# Documentación: La Asfixia del Espacio Mediático

Este documento detalla el proceso periodístico y técnico detrás de la visualización interactiva sobre la invisibilidad de la fauna amenazada en la prensa chilena durante los últimos seis meses.

## 1. Proceso de Visualización y Decisiones Tomadas

La visualización fue concebida como un **Muro de la Invisibilidad** utilizando la librería **Altair** en Python. Las decisiones clave fueron:

* **Selección del Formato:** Se optó por un gráfico de mosaico (rectángulos proporcionales) para representar físicamente cómo unas pocas especies "asfixian" el espacio disponible, dejando franjas casi imperceptibles para las especies menos carismáticas.
* **Identidad Visual:** Se aplicó una paleta basada en la urgencia biológica: **Naranja (#F57C00)** para especies en Peligro Crítico (CR) y **Verde (#4CAF50)** para especies En Peligro (EN).
* **Soluciones de Legibilidad:** Debido a la compresión del espacio, se decidió **rotar el texto a 270 grados** y aplicar un filtro de visibilidad donde solo las especies con 4 o más apariciones muestran su nombre, evitando la superposición y reforzando la metáfora de la invisibilidad para el resto.
* **Interactividad:** Se incorporó una **ficha técnica flotante** (tooltip) para que el lector pueda recuperar la información de las especies "fantasma" al interactuar con el gráfico.

## 2. Gestión de la Base de Datos

La base de datos fue seleccionada tras un monitoreo de prensa nacional de los últimos seis meses. Se eligió este corpus porque permite contrastar la **frecuencia de menciones** con el **protagonismo real** de la especie en el relato periodístico.

### Procesamiento de datos:
1.  **Limpieza:** Se estandarizaron los nombres científicos y las categorías RCE.
3.  **Filtrado Editorial:** Se descartaron categorías y/o noticias que no aportaban al foco narrativo para concentrar la atención en la crisis de las especies en mayor riesgo.

## 3. Preguntas que responde la visualización

* ¿Cómo se distribuye el interés de la prensa entre las especies en peligro crítico?
* ¿Existe una correlación entre el riesgo biológico y la cantidad de noticias publicadas?
* ¿Qué especies son "dueñas" de la conversación pública y cuáles son meros datos estadísticos?
* ¿Cuántas especies en peligro crítico pasan desapercibidas (tienen solo una mención) en el último semestre?

## 4. Observaciones

Se observa un **sesgo carismático**: especies como el pingüino de Humboldt dominan el espacio no solo por su estado de riesgo, sino por su valor iconográfico, mientras que anfibios e insectos con el mismo nivel de amenaza permanecen en el anonimato mediático.